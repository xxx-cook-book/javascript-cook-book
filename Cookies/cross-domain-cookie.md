# Cross Domain Cookie

## Back-end

* Django

  ```python
  # -*- coding: utf-8 -*-

  class AccessControlAllowOriginMiddleware(object):
      
      def process_response(self, request, response):
          response['Access-Control-Allow-Origin'] = 'http://tt4it.com:'
          response['Access-Control-Allow-Credentials'] = 'true'
          return response
  ```
  * ``Access-Control-Allow-Origin`` can't be ``'*'``

## Front-end

* jQuery / Zepto

  ```javascript
  $.ajax({
      url: 'url',
      type: 'POST',
      data: {},
      xhrFields: {
          withCredentials: true
      },
      crossDomain: true,
      success: function (response) {},
      error: function (response) {}
  })
  ```

## References

