
import {fromEvent, Observable, Subscription} from 'rxjs';
import { concatMap, map, switchMap, filter, take} from 'rxjs/operators';
import { timer, BehaviorSubject } from 'rxjs';
import { HttpClient } from '@angular/common/http';


export interface ServerResponse{
  generated: boolean
}

export class AppComponent implements OnInit {
  loading$ = new BehaviorSubject('');

  constructor(private router: Router, private http: HttpClient) { }

  ngOnInit() {
      const url$ = this.http.get('my-api-url');
      this.loading$.pipe(
         switchMap(_ => timer(0, 100).pipe(
           concatMap(_ => url$),
           map((response: ServerResponse) => {
            return response;
           })
         ).pipe(filter(data => data.generated===true))
         .pipe(take(1))
        )
      )
      .subscribe(()=> {console.log('done')})
  }

  ngOnDestroy(): void {
    /**
    * Unsubscribe all subscriptions to avoid memory leak
    */
    //here will do unsubscribe
  }
}

//Import the HttpClientModule in app.module.ts if not used then we can't able to hit api
