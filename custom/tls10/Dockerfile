# 自定义 JRE
# 我们开启 TLSv1, TLSv1.1 , 兼容 sqlserver 2012
# sed 逐行处理,但是 disabledAlgorithms 里面有换行符,所以字符串替换只截取了一部分
FROM jdk17:dev

ARG original_DisabledAlgorithms="jdk.tls.disabledAlgorithms=SSLv3, TLSv1, TLSv1.1, RC4, DES, MD5withRSA"
ARG customize_DisabledAlgorithms="jdk.tls.disabledAlgorithms=SSLv3, RC4, DES, MD5withRSA"

RUN sed -i "s/$original_DisabledAlgorithms/$customize_DisabledAlgorithms/g" ${JAVA_HOME}/conf/security/java.security \
    && cat ${JAVA_HOME}/conf/security/java.security

