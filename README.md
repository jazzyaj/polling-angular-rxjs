# polling-angular-rxjs

install RsJS library using npm install rxjs --save
than import essential operators from rxjs/operators

app.component.ts file is holding the RxJS observable part which will start polling on every 100ms when ever the response is {'generated':true} will stop polling automatically.

http-api file is there on which polling sccuess response will be handle based in polling id
