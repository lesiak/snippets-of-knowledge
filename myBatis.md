# Transactions
#2.3.5

```java
com.ibatis.sqlmap.engine.impl.SqlMapExecutorDelegate {  
  /**
   * Execute an update statement
   *
   * @param sessionScope - the session scope
   * @param id      - the statement ID
   * @param param   - the parameter object
   * @return - the number of rows updated
   * @throws SQLException - if the update fails
   */
  public int update(SessionScope sessionScope, String id, Object param) throws SQLException {
    int rows = 0;

    MappedStatement ms = getMappedStatement(id);
    Transaction trans = getTransaction(sessionScope);
    boolean autoStart = trans == null;

    try {
      trans = autoStartTransaction(sessionScope, autoStart, trans);

      StatementScope statementScope = beginStatementScope(sessionScope, ms);
      try {
        rows = ms.executeUpdate(statementScope, trans, param);
      } finally {
        endStatementScope(statementScope);
      }

      autoCommitTransaction(sessionScope, autoStart);
    } finally {
      autoEndTransaction(sessionScope, autoStart);
    }

    return rows;
  }
}

    ```