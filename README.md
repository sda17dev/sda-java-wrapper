# Java Wrapper for the Seoul Digital Archives's API


Javadoc available at: https://sda17dev.github.io/sda-dev-docs/docs/doc10.html


This is meant to be a simple Java wrapper for the Seoul Digital Archives(SDA)'s API

https://archives.seoul.go.kr




## Examples
--------------------------------

Before anything is done you must set your apikey.


    SearchQuery sq = new SearchQuery("pizza",null);
        
    sq.setAPIKEY("your api key goes here");



Every SearchQuery will return an array full of SDA's records. You can then gain access to each records information from there.

You can execute a search with:

* Just a Search Query
* Search Query & SearchOptions
* Just SearchOptions

If you only want one, then just pass null for the other.

### Execute a simple search query WITHOUT any SearchOptions.

    SearchQuery sq = new SearchQuery("pizza",null);
        
        sq.setAPIKEY("your api key goes here");
        SdaItem[] result = sq.search();

        for (SdaItem dp : result) {
            System.out.println(dp.getSourceResource().getTitle());
        }

### Execute a search query with some SearchOptions


    
    SearchOptions so = new SearchOptions();

    so.description="history";
    SearchQuery sq = new SearchQuery("pizza",null);
        
        sq.setAPIKEY("your api key goes here");
        SdaItem[] result = sq.search();

        for (SdaItem dp : result) {
            System.out.println(dp.getSourceResource().getTitle());
        }




