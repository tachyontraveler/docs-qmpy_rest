.. role:: query-url(literal)
.. role:: field(literal)

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

URL Format
~~~~~~~~~~

Query Fields
------------
    -  :field:`filter`: customized filters, e.g. 'element_set=O AND ( stability<-0.1 OR delta_e<-0.5 )'
    -  :field:`limit`: number of data return at once
    -  :field:`offset`: the offset of data return
    -  :field:`fields`: return subset of fields, e.g. 'name,id,delta_e', '!sites'
    1. :field:`composition`: compostion of the materials or phase space, e.g. Al2O3, Fe-O
    2. :field:`element_set`: the set of elements that the compound must have, '-' for OR, ',' for AND, e.g. (Fe-Mn),O
    3. :field:`icsd`: whether the structure exists in ICSD, e.g. False, True, F, T
    4. :field:`prototype`: structure prototype of that compound, e.g. Cu, CsCl
    5. :field:`generic`: chemical formula abstract, e.g. AB, AB2
    6. :field:`spacegroup`: the space group of the structure, e.g. Fm-3m
    7. :field:`natoms`: number of atoms in the supercell, e.g. 2, >5
    8. :field:`volume`: volume of the supercell, e.g. >10
    9. :field:`ntypes`: number of elements types in the compound, e.g. 2, <3
    10. :field:`stability`: hull distance of the compound, e.g. 0, <-0.1,
    11. :field:`delta_e`: formation energy of that compound, e.g. <-0.5,
    12. :field:`band_gap`: band gap of the materials, e.g. 0, >2
    
Response Format
~~~~~~~~~~~~~~~

Format file types
-----------------

Response keys
-------------

More Example Queries
~~~~~~~~~~~~~~~~~~~~
1. :query-url:`http://oqmd.org/oqmdapi/formationenergy?fields=name,entry_id,icsd_id,prototype,ntypes,natoms,volume,delta_e,band_gap,stability&limit=50&offset=0&sort_offset=0&noduplicate=False&desc=False&filter=stability<0.5 AND element_set=(Al-Fe),O AND (ntypes>=3 AND natoms<9) OR ntypes<3`
 Here, the `filter` key contains a logical expression using `AND` and `OR` functions
2. :query-url:`http://oqmd.org/`

Practical Data Retrieval
~~~~~~~~~~~~~~~~~~~~~~~~

Command line
------------

Web Browser
-----------
