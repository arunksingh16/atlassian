ARG IMG_TAG=8.13.6
FROM atlassian/jira-software:$IMG_TAG
RUN mkdir ${JIRA_INSTALL_DIR}/userpref
RUN chown -R ${RUN_USER}:root        ${JIRA_INSTALL_DIR} \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/userpref \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/temp \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/work \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/logs \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/bin \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/conf \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/webapps \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/lib \
    && chmod -R 777                  ${JIRA_INSTALL_DIR}/atlassian-jira
COPY entrypoint.py \
     docker-shared-components/image/entrypoint_helpers.py  /
