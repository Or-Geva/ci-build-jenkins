timeout(time: 45, unit: 'SECONDS'){
   node {
      response = httpRequest (consoleLogResponseBody: true, 
         contentType: 'APPLICATION_JSON', 
         httpMode: 'GET', 
         url: BADGE_LINK, 
         validResponseCodes: '200')
      body = response.content.toLowerCase()
      if (body.contains("failing")) {
          currentBuild.result = 'FAILURE'
      } else if (body.contains("passing")) {
          currentBuild.result = 'SUCCESS'
      } else {
          currentBuild.result = 'NOT_BUILT'
      }
   }
}
