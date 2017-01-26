FROM cheempz/java_appservers:j7_tomcat7

ENV STACK_APPS='test-axis-min test-cxf-min test-glassfish-jersey-min \
    test-glassfishws-min test-jax-ws-min test-jersey-min test-rest-server \
    test-resteasy-min test-resttemplate-min test-soap-server test-xml-soap-min \
    test-apache-httpclient3 test-apache-httpclient4 test-apache-httpclient4.4 \
    test-axis test-cxf test-glassfish-jersey test-glassfishws test-jax-ws \
    test-jersey test-resteasy test-resttemplate test-xml-soap'

RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

WORKDIR $CATALINA_HOME/webapps

RUN for app_name in $STACK_APPS ; do \
        curl -L -o ${app_name}.war https://s3.amazonaws.com/apm-qa-automation/java/compiled-test-apps/${app_name}.war-latest ; \
    done

WORKDIR $CATALINA_HOME