# 自定义 JRE
# 我们开启 TLSv1, TLSv1.1 , 兼容 sqlserver 2012
# 考虑基于 https://github.com/corretto/corretto-docker/tree/main/17/headless/al2023 体积能减小 80MB

FROM amazoncorretto:17

ARG original_DisabledAlgorithms="jdk.tls.disabledAlgorithms=SSLv3, TLSv1, TLSv1.1, RC4, DES, MD5withRSA"
ARG customize_DisabledAlgorithms="jdk.tls.disabledAlgorithms=SSLv3, RC4, DES, MD5withRSA"

RUN sed -i "s/$original_DisabledAlgorithms/$customize_DisabledAlgorithms/g" ${JAVA_HOME}/conf/security/java.security
