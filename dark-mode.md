paths:
  /user/settings:
    post:
      summary: Управление темным режимом.
      description: Включает автоматический темный режим интерфейса. Утилита сама активирует его после 18:00 на основе системного времени.
      requestBody:
          required: true
          content:
            application/json:
              schema:
                type: object
              example:
                dark_mode: true
      responses:
        '204':
          description: Настройки успешно применились.
        '401':
          description: Пользователь не авторизован (отсутствует токен).
    ```json
    {
      "status": "success",
      "condition": {
        > 204 Dark mode activated.
        > 401 User not authorized.
      }
    }