;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;Enterprise�\�z�������c�[���g�p���@
; Linux �� �� Enterprise�̊�{�\�����\�z����
;
;  ��Host OS                  ���쐬�����
;    Windows                    GuestOS + Enterprise
; +-----------------+        +------------------+
; |   TeraTerm  +-------------+ArcGIS Server    |
; |    WinSCP       |        | ArcGIS Datastore |
; +-----------------+        | ArcGIS Webadaptor|
;                            | ArcGIs Portal    |
;                            +------------------+
;Guest OS�̊�]�X�y�b�N
;CPU(�R�A��) 4 Core
;Memory      16G
;HDD         60G�ȏ�
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;


���O�����
�EHost OS(Windows)��Tera Term���C���X�g�[������Ă��邱�ƁB
�E���L�T�[�o�ɓ���邱��
�EGuestOS(Redhat or CentOS)���쐬����Ă��邱��
��2020�N7��29�����_�ł�2��OS�݂̂��T�|�[�g����Ă��邱�Ƃ���

���t�H���_�̒��g

    00_rhel76_env_setting.ttl:
    10_portal_install.ttl    : Portal for ArcGIS��Install�����site�̍쐬�����܂��B
    20_server_install.ttl    : ArcGIS Server��Install�����site�̍쐬�����܂��B
    30_datastore_install.ttl : ArcGIS Datastore��Install�����site�̍쐬�����܂��B
    40_webadaptor_install.ttl: ArcGIS Webadaptor��Install�����site�̍쐬�����܂��B
    41_setting_warfile.ttl   : war�t�@�C����tomcat/webapps�ȉ��ɔz�u
    42_auto_start.ttl        : Portal,Server,Datastore��OS�N�����Ɏ����N������ݒ�B
    43_web_server.ttl        : WebAdaptor�o�R��Server�ɐڑ�����ݒ�
    44_web_portal.ttl        : WebAdaptor�o�R��Portal�ɐڑ�����ݒ�
    50_get_enterprise.ttl    : 10.7��������10.7.1��Enterprise�̃A�[�J�C�u���擾����B
    51_unzip_enterprise.ttl  : �擾�����A�[�J�C�u����
    52_patch.ttl             : �񋟂���Ă���patch���擾�A�K��������B
    999_setting.ttl          : �T�[�o�̏����L�ڂ���
    99_login.ttl             : ���[�U�[���O�C������
    99_super_login.ttl       : �X�[�p�[���[�U�[�Ń��O�C������
    master_exe.ttl           : ���̃}�N�������s����ƋL�ڂ���Ă���}�N�������s����AEnterprise�����쐬�����

�����ꂼ��P�̂Ń}�N�������s�����邱�Ƃ��ł��܂��B
  �Ⴆ��Enterprise�̃A�[�J�C�u�����擾�������ꍇ��50_get_enterprise.ttl�����s����Ύ擾�ł��܂��B

��50_get_enterprise.ttl�ɂ���
  "\\ejfilesvr\���i���f�B�A"����擾���Ă��邽�߁AHost OS ���狤�L�T�[�o�ɓ���邱�Ƃ����O�Ɋm�F���Ă��������B
  �}�N�������s�����炢�����̑I�����o�Ă��܂��̂ŉ񓚂��Ă��������B


���g�p�菇
�P.	999_setting.ttl�ɕK�v�ȋL�q���e�L�X�g�G�f�B�^����s���Ă��������B
�Q.	1�̃T�[�o����Enterprise���\�z����ꍇ��master_exe.ttl�����s���Ă��������B

��������Ƃ�������
�T�N���G�f�B�^��TeraTerm�}�N�����J����ctl+b�Ń}�N�������s�ł���
