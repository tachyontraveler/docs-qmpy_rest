.. role:: query-url(literal)

Introduction
============

RESTful API is now supported at oqmd.org!
     
- For example, a simple request may be made like this 
:query-url:`http://oqmd.org/oqmdapi/formationenergy?fields=name,entry_id,spacegroup,ntypes,band_gap,delta_e&filter=element_set=(Al-Fe),O`:

    .. code:: jsonc

     {
       "links": {
        "next": "http://oqmd.org/oqmdapi/formationenergy?fields=name%2Centry_id%2Cspacegroup%2Cntypes%2Cband_gap%2Cdelta_e&filter=element_set%3D%28Al-Fe%29%2CO&icsd=True&limit=2&offset=2",
        "previous": null,
        "base_url": {
            "href": "http://oqmd.org/oqmdapi",
            "meta": {
                "_oqmd_version": "1.0"
            }
        }
       },
       "resource": {},
       "data": [
        {
            "name": "NaAlH2CO5",
            "entry_id": 16974,
            "spacegroup": "Imma",
            "ntypes": 5,
            "band_gap": 5.255,
            "delta_e": -2.05739610121138
        },
        {
            "name": "CaAl2SiH4O8",
            "entry_id": 16995,
            "spacegroup": "I41/a",
            "ntypes": 5,
            "band_gap": 5.087,
            "delta_e": -2.49008973723542
        }
       ],
       "meta": {
        "query": {
            "representation": "/formationenergy?fields=name,entry_id,spacegroup,ntypes,band_gap,delta_e&icsd=True&limit=2&filter=element_set=(Al-Fe),O"
        },
        "api_version": "1.0",
        "time_stamp": "2019-10-08 15:13:12",
        "data_returned": 2,
        "data_available": 1078,
        "comments": "",
        "query_tree": "",
        "more_data_available": true
       },
       "response_message": "OK"
     }

- Filter keys
- Fields
- Response format specifiers
