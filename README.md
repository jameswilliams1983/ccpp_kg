ontology/ccpp_ontology.ttl defines the vocabulary: the types of things that exist in any carbon capture plant (Column, HeatExchanger, Pump, FlowSensor, Stream) and the relationships between them (feedsInto, hasSensor, hasAlarmHigh). Written in Turtle, not Python. This is shared with the full plant later.

stripping_loop/build_stripping_loop.py is where the stripping loop KG gets built. It loads the ontology, then adds the actual equipment in your loop (the stripper, reboiler, condenser, reflux drum, lean/rich exchanger, pumps, sensors) with their P&ID tags, connections and operating limits. At the end it saves everything to a file called stripping_loop.ttl, which is your finished KG.

stripping_loop/test_queries.py loads stripping_loop.ttl and runs your SPARQL queries against it, checking each one returns what you expect (for example "what is downstream of the reboiler?" or "which sensors have a high alarm above X?").
