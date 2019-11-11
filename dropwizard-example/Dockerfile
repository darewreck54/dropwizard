FROM gcr.io/google_appengine/openjdk8

ADD target/dropwizard-example-2.0.0-rc13-SNAPSHOT.jar dropwizard-example-2.0.0-rc13-SNAPSHOT.jar

ADD example.keystore example.keystore

ADD example.yml example.yml

RUN java -jar dropwizard-example-2.0.0-rc13-SNAPSHOT.jar db migrate example.yml
CMD java -agentpath:/opt/cdbg/cdbg_java_agent.so  -Dcom.google.cdbg.module=dropwizard-example -Dcom.google.cdbg.version=1000 -jar dropwizard-example-2.0.0-rc13-SNAPSHOT.jar server example.yml

EXPOSE 8080