Ant�AMaven ����� Gradle �Ƃ̓����Ɋւ�������́ADTP_Engines_for_Java_User_Manual.pdf �t�@�C������� plugins-manual.html �ɂ���܂��B
�����̃}�j���A���́Amanuals/ja �f�B���N�g���ɂ���܂��B

�ȉ��̎菇�́ADemo �v���W�F�N�g�ɑ΂��� Static Analysis Engine (SAE) �����
Code Coverage Engine (CCE) ��L���ɂ��� Unit Tests Connector (UTC) �����s����
���@�ł��B

Demo �p�̐ݒ肪 [INSTALL]/examples/demo �f�B���N�g���� demo.properties �t�@�C���Ƃ��Ē񋟂���Ă��܂��Bdemo.properties �t�@�C���� Ant�AMaven�AGradle �̃r���h
�X�N���v�g�Ŏg�p�ł��܂��B�ȉ��̃R�}���h ���C���̗�́ADemo �v���W�F�N�g�̃f�B���N�g��
������s���邱�Ƃ�O��Ƃ��Ă��܂��B


�O�����
-------------------------------------------------
1. �C���X�g�[�� �f�B���N�g���ɂ��� jtestcli.properties �� Jtest DTP Engine �̃��C�Z���X���ݒ肳��Ă���K�v������܂��B


Jtest DTP Engine �̃f�[�^ �t�@�C��
-------------------------------------------------
1. �ÓI��� (SAE) �����s����ɂ́A���̃R�}���h�𒼐ڎg�p���� �uRecommended Rules�v�R���t�B�M�����[�V���������s���܂��B
   Windows:
     ..\..\jtestcli.exe -config "builtin://Recommended Rules" -data demo.data.json -report report
   UNIX:
     ../../jtestcli -config "builtin://Recommended Rules" -data demo.data.json -report report

Ant
-------------------------------------------------
1. ant ���p�X�Ɋ܂܂�Ă��邱�Ƃ��m�F���܂��B
2. �ÓI��� (SAE) ����ђP�̃e�X�g (UTC) �����s���ăJ�o���b�W (CCE) �����|�[�g����ɂ́A�uDemo Configuration�v�R���t�B�M�����[�V���������s���܂��B
     
     ant -file jtest.xml
     (Ant 1.6 �̏ꍇ�A�R�}���h���C�� �I�v�V���� " -lib lib/junit-4.11.jar" ��ǉ����܂��B���̃I�v�V�������Ȃ��ƁA�e�X�g�͎��s�ł��܂���)

   Demo �v���W�F�N�g���r���h����A�P�̃e�X�g�����s����܂��BAnt �v���O�C���̓\�[�X �R�[�h�̃R���p�C�� �f�[�^�����W���A��͂����s���ăJ�o���b�W���ƂƂ��Ƀe�X�g���ʂ����W���A���|�[�g�𐶐����܂��B

   ����:
   
   �ÓI��� (SAE) ���������s����ɂ́A���̃R�}���h���g�p���܂�:
     
     ant -file jtest.xml jtest-sae
   
   �P�̃e�X�g (UTC) ���������s����ɂ́A���̃R�}���h���g�p���܂��B:
     
     ant -file jtest.xml jtest-utc
     (Ant 1.6 �̏ꍇ�A�R�}���h���C�� �I�v�V���� " -lib lib/junit-4.11.jar" ��ǉ����܂��B���̃I�v�V�������Ȃ��ƁA�e�X�g�͎��s�ł��܂���)
       
   �R���t�B�M�����[�V������ jtest.xml �Ŏw�肳��Ă��܂��Bjtest�Ajtest-sae�A�܂��� jtest-utc
   �^�[�Q�b�g���Q�Ƃ��Ă��������B


Maven
-------------------------------------------------
1. mvn ���p�X�Ɋ܂܂�Ă��邱�Ƃ��m�F���܂��B
2. ���̃K�C�h�ɏ]���� Maven ��ݒ肵�܂��B
   manuals/ja/plugins-manual.html: [Jtest Maven Plugin] > [�g�p���@] > [�����Z�b�g�A�b�v]

3. �ÓI��� (SAE) ����ђP�̃e�X�g (UTC) �����s���ăJ�o���b�W (CCE) �����|�[�g����ɂ́A�uDemo Configuration�v�R���t�B�M�����[�V���������s���܂��B
    mvn clean test-compile jtest:agent test jtest:jtest -Djtest.config="builtin://Demo Configuration"
    (�܂��� mvn clean test-compile jtest:instrument test jtest:jtest -Djtest.config="builtin://Demo Configuration")
  
   �T���v�� �v���W�F�N�g���r���h����A�P�̃e�X�g�����s����܂��BMaven �v���O�C���̓\�[�X �R�[�h�̃R���p�C�� �f�[�^�����W���A��͂����s���ăJ�o���b�W���ƂƂ��Ƀe�X�g���ʂ����W���A���|�[�g�𐶐����܂��B

   ����:
   
   �ÓI��� (SAE) ���������s����ɂ́A���̃R�}���h���g�p���܂�:
   
     mvn jtest:jtest
   
   �f�t�H���g�� �uRecommended Rules�v�R���t�B�M�����[�V�������g�p����܂��B

   �P�̃e�X�g (UTC) ���������s����ɂ́A���̃R�}���h���g�p���܂��B:
   
    mvn clean test-compile jtest:agent test jtest:jtest -Djtest.config="builtin://Unit Tests"
    (�܂��� mvn clean test-compile jtest:instrument test jtest:jtest -Djtest.config="builtin://Unit Tests")


Gradle
-------------------------------------------------
1. gradle ���p�X�Ɋ܂܂�Ă��邱�Ƃ��m�F���܂��B
2. �C���X�g�[���ς݂� Jtest DTP Engine �p�b�P�[�W��ݒ肷�邩�A�r���h�X�N���v�g�� jtest �u���b�N�ɔC�ӂ̐ݒ��ǉ����܂��B

3. �ÓI��� (SAE) ����ђP�̃e�X�g (UTC) �����s���Č��ʂ����|�[�g����ɂ́A�uDemo Configuration�v�R���t�B�M�����[�V���������s���܂��B

     gradle clean jtest-agent test jtest -Djtest.config="builtin://Demo Configuration"
     (�܂��� gradle clean jtest-instrument test jtest -Djtest.config="builtin://Demo Configuration")

   �T���v�� �v���W�F�N�g���r���h����AJunit �e�X�g�����s����܂��BGradle �v���O�C���̓\�[�X �R�[�h�̃R���p�C�� �f�[�^�����W���A��͂����s���ăe�X�g���ʂ����W���A���|�[�g�𐶐����܂��B

   ����:
   
   �ÓI��� (SAE) ���������s����ɂ́A���̃R�}���h���g�p���܂�:
     
     gradle clean build jtest
   
   �f�t�H���g�� �uRecommended Rules�v�R���t�B�M�����[�V�������g�p����܂��B

   �P�̃e�X�g (UTC) ���������s����ɂ́A���̃R�}���h���g�p���܂��B:
   
     gradle clean jtest-agent test jtest -Djtest.config="builtin://Unit Tests"
     (�܂��� gradle clean jtest-instrument test jtest -Djtest.config="builtin://Unit Tests")


=================================================
�A�v���P�[�V���� �J�o���b�W�̎��W

1. "mvn" ����� java ���p�X�ɐݒ肳��Ă��邱�Ƃ��m�F���܂��B

2. ���̃K�C�h�ɏ]���� Maven ��ݒ肵�܂��B
    manuals/ja/plugins-manual.html: [Jtest Maven Plugin] > [�g�p���@] > [�����Z�b�g�A�b�v]

3. �A�v���P�[�V�������r���h���A���j�^�����O�ɕK�v�ȃf�[�^�����W���܂��B
     mvn clean package jtest:monitor
   
   ����: ���ʂƂ��� monitor.zip �t�@�C����������͂��ł��B

4. �A�v���P�[�V���������s���ăJ�o���b�W �f�[�^�����W���܂��B
   
   Windows:
     
     a) monitor.zip �A�[�J�C�u�� demo �f�B���N�g���ɓW�J���܂� (monitor �Ƃ����T�u�f�B���N�g�����쐬����܂�)�B
        Archive path: target\jtest\monitor\monitor.zip
     
     b) agent.bat �����s���܂��B
        cd monitor        
        agent.bat
        cd ..
      
     c) �X�e�b�v b) �Ő������ꂽ Java VM �������g���ăA�v���P�[�V���������s���܂��B
        java -cp target\Demo.jar [�X�e�b�v b) �Ő������ꂽ Java VM ������\��t����] examples.stackmachine.RunnableStackMachine

     d) "Stack Machine Example" �A�v���P�[�V�������g���Ă������A�N�V���������s���܂��B
        - Insert 123 number into "Input" field
        - press "push" button 5 times
        - press "+", "-", "x" and "/" buttons
        - exit application

   UNIX:

     a) monitor.zip �A�[�J�C�u�� demo �f�B���N�g���ɓW�J���܂� (monitor �Ƃ����T�u�f�B���N�g�����쐬����܂�)�B
        unzip ./target/jtest/monitor/monitor.zip
     
     b) agent.sh �����s���܂��B
        ./monitor/agent.sh
      
     c) �X�e�b�v b) �Ő������ꂽ Java VM �������g���ăA�v���P�[�V���������s���܂��B
        java -cp ./target/Demo.jar [�X�e�b�v b) �Ő������ꂽ Java VM ������\��t����] examples.stackmachine.RunnableStackMachine

     d) "Stack Machine Example" �A�v���P�[�V�������g���Ă������A�N�V���������s���܂��B
        - Insert 123 number into "Input" field
        - press "push" button 5 times
        - press "+", "-", "x" and "/" buttons
        - exit application

5. �J�o���b�W ���|�[�g�𐶐����܂��B

     Windows:  
       ..\..\jtestcli.exe -config "builtin://Calculate Application Coverage" -staticcoverage monitor\static_coverage.xml -runtimecoverage monitor\runtime_coverage
     UNIX
       ../../jtestcli -config "builtin://Calculate Application Coverage" -staticcoverage ./monitor/static_coverage.xml -runtimecoverage ./monitor/runtime_coverage

     �J�o���b�W�̏ڍׂ� report.html �Ŋm�F�ł��܂��B


