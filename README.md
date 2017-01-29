# nVidiaGguOpenCLsdk


＃nVidiaGguOpenCLsdk

-------------------------------------------------- ------------------------------
-------------------------------------------------- ------------------------------
NVIDIA GPUコンピューティングソフトウェア開発キット
OpenCL SDK 4.2リリースノート
R295およびR300リリースドライバ

  Windows XP、Windows Vista、およびWindows 7（32/64-bit）
  Windows Server 2003、2003 R2、2008、2008 R2
  Linux OS（32/64-bit）
  Mac OSX（10.6.x SnowLeopard 32/64-bit、10.7.x Lion 32/64-bit）

-------------------------------------------------- ------------------------------
-------------------------------------------------- ------------------------------

-------------------------------------------------- ------------------------------
目次
-------------------------------------------------- ------------------------------
私は法的通知
II A Windowsのインストール手順
II B Linuxのインストール手順
III A SDKインフラストラクチャを使用してWindows用に独自のOpenCLプログラムを作成する
III B SDKインフラストラクチャを使用したLinux用の独自のOpenCLプログラムの作成
IV A SDKインフラストラクチャの外でWindows用に独自のOpenCLプログラムを作成する
IV B SDKインフラストラクチャの外部でLinux用に独自のOpenCLプログラムを作成する
V. Mac OSXの既知の問題
V. B Linuxでの既知の問題
VI。よくある質問
VII。ログの変更
VIII。 OSプラットフォームとコンパイラのサポート
-------------------------------------------------- ------------------------------

-------------------------------------------------- ------------------------------
I.法的通知
-------------------------------------------------- ------------------------------
注意：このリリースは、
このリリースで配布されるエンドユーザー使用許諾契約書（EULA）。あなたが受け入れない場合
EULAには、このリリースに含まれるファイルを使用する権利がありません。
このリリースに関連するすべてのファイルのすべてのコピーを直ちに削除してください。

-------------------------------------------------- ------------------------------
II.A. Windowsのインストール手順
-------------------------------------------------- ------------------------------

1. NVIDIA GPU Computing SDKに含まれているOpenCL SDKサンプルには、CUDA ComputeでのGPUが必要です
   適切に動作するアーキテクチャ。 CUDAアーキテクチャコンピューティング対応GPUの完全なリストについては、
   オンラインのリストを参照してください：http://www.nvidia.com/object/cuda_learn_products.html

2. NVIDIA GPU Computing SDKのOpenCL SDKサンプルには、NVIDIAのバージョン295.xxまたは300.xxが必要です
   32ビットまたは64ビットのWindows XP、Windows VistaまたはWindows 7で実行するには、Display Driver以降が必要です。
   この必須ドライバは、このリンクを介して公に利用可能です。

   http://www.nvidia.com/Download/index.aspx?lang=en-us
   
   ドライバインストールのヒントドキュメントを必ずお読みください
   ドライバをインストールします。http://www.nvidia.com/object/driver_installation_hints.html

       NVIDIAドライバをダウンロードするには、このリンクを参照してください。
       
       http://www.nvidia.com/page/pg_20030521269172.html
   
3.このSDKには、Microsoft DirectX SDKに依存するOpenCL / DirectX interop SDKサンプルが含まれています。
   これらのサンプルを作成するには、2010年6月からMicrosoft DirectX SDKをダウンロードするか、
   このリンクから新しい
       
       http://msdn.microsoft.com/en-us/directx/default.aspx
   
4.以前のバージョンのNVIDIA GPU Computing SDKをアンインストールします

5.ご使用のOSに付属のインストーラを実行して、NVIDIA GPU Computing SDKをインストールします。
    
   OpenCL SDKのデフォルトのインストールフォルダは次のとおりです。

   Windows XP
       C：\ Documents and Settings \ All Users \ Application Data \ NVIDIA Corporation \ NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL

   Windows Vista
       C：\ ProgramData \ NVIDIA Corporation \ NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL
           
   注意：「アプリケーションデータ」および「ProgramData」フォルダは、「Windowsエクスプローラ」でデフォルトとして非表示になっている可能性があります。
          多くのWindowsインストールで。必要に応じて、「Windowsエクスプローラ」で表示することができます。
          これを行うには、Windowsファイルの[ツール]メニューの[フォルダオプション]の設定を変更します
冒険者。
      
6. SDKをインストールしたら、[スタート]メニューから[NVIDIA GPU Computing]をクリックしてSDKブラウザを開きます
   NVIDIA Corporationプログラムグループ内のNVIDIA GPU Computingフォルダの「SDK Browser」
   Windowsの[スタート]メニューにインストールされます。

       - インストールされている各SDKサンプルプログラムが、実行可能ファイルを実行するためのリンクとともに表示されます。
        ソースコードファイルを表示します。
 
       - サンプルのいくつかは、さらに、サンプルを詳細に記述したホワイトペーパーへのリンクを提示します。
 
       - サンプルは、SDKブラウザ内で、複雑さのおおよその順に表示されます
        複雑なプロジェクトは最上部にあり、最も複雑なプロジェクトは最下部にあります。

7. 32ビットまたは64ビットのビルド（インストールOSと一致）、リリースおよびデバッグ
   SDKプロジェクトの全セットとユーティリティ依存関係の設定
   提供されるソリューション：

      Visual Studio 2005（VC8）用の "oclRelease_vs2005.sln"
Visual Studio 2008（VC9）用の "oclRelease_vs2008.sln"
Visual Studio 2010（VC10）の "oclRelease_vs2010.sln"

   これらの.slnファイルは、 "\ NVIDIA GPU Computing SDK 4.2 \ OpenCL"ディレクトリにインストールされます
   SDKのSDKサンプルの実行可能ファイル（* .exe）と関連するファイル（* .lib）と（* .dll）をビルドまたはコピーし、
   現在のOSで実行バイナリを適切なディレクトリに配置する
   "\ NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ bin \ <platform> \ <configuration>"
   
   その後のビルドでは、
       - 各サンプルのディレクトリにある個々のソリューションファイルを
        "NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ src"、または
        
       - "\ NVIDIA GPU Computing SDK 4.2 \ OpenCL"にあるグローバルソリューションファイルを使用します。
"oclRelease_vs2005.sln"
"oclRelease_vs2008.sln"
"oclRelease_vs2010.sln"
   
8. NVIDIA GPU Computing SDKのOpenCL部分のビルド構造に関する注意事項：

8. NVIDIA GPU Computing SDKのOpenCL部分のビルド構造に関する注意事項：
      
       - "$（PlatformName）"（VS2005 / VS2008）または "$（プラットフォーム）"（VS2010）はVisual Studioで使用されています
SDKのプロジェクトを使用して、正しいOpenCL.libファイルのバージョン（Win32またはx64）に切り替えます。
"NVIDIA GPU Computing SDK 4.2 \ OpenCL \ lib"フォルダにあります。これはビルド時に必要なstublibファイルです
OpenCL dllに暗黙的にリンクするための時間。システムにインストールされている
適切なNVIDIA GPUドライバ。
        
       - ビルド後にポストビルドイベントが実行されます。
"oclRelease_vs2005.sln"、
"oclRelease_vs2008.sln"、
"oclRelease_vs2010.sln"
そして
"oclUtils_vs2005.sln"、
"oclUtils_vs2008.sln"、
"oclUtils_vs2010.sln"

必要なdllがディレクトリ内にコピーされる
"NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ bin \ <platform> \ <configuration>"

        （上記の6項で説明した* .exeファイルを含む同じディレクトリ）。これは置く
        DLLは実行時にWindowsによって検索される最初のデフォルトパスの場所にあります。

       - NVIDIA GPU Computing SDKのサンプルは、静的に呼び出されたユーティリティライブラリにリンクされています
        "shrUtils"はOpenCLとは無関係の一般的なC ++ユーティリティのセットですが、
        NVIDIA GPU Computing APIのサンプルデモアプリケーションを作成します。

           - 上記の手順6を実行すると、開発者はshrUtilsを気にする必要はありません。この依存関係
            ステップ6で世話をする。しかし、開発者はshrUtilsのソースコードを
"\ NVIDIA GPU Computing SDK 4.2 \ shared \"のソリューションファイル：

            "shrUtils_vs2005.sln"
"shrUtils_vs2008.sln"
"shrUtils_vs2010.sln"
        
           - SDKサンプルのリリース版は、shrUtils [32 | 64] .libにリンクしています。デバッグバージョン
            これらのサンプルのうち、shrUtils [32D | 64D] .libにリンクしています。
            
           - shrUtils_vs2005 / 08 / 10.slnコンパイルの出力はプロジェクト設定で設定され、
            サブディレクトリ "NVIDIA GPU Computing SDK 4.2 \ shared \ lib"
            
           - shrUtilsは、便宜上、このSDKで提供され、使用されています。それは必要ない
            独立したOpenCLアプリケーション開発。

       - NVIDIA GPU Computing SDKのOpenCLサンプルも、静的にリンクされているユーティリティライブラリにリンクされています
        OpenCL関連またはOpenCL SDK固有のユーティリティのセットであり、共通でもある "oclUtils"
        ほとんどの標準システムのヘッダーにはshrUtilsが含まれています。
        
           - 上記の手順6を実行すると、開発者はoclUtilsを心配する必要はありません。この依存関係
            ステップ6で世話をする。しかし、開発者はoclUtilsのソースコードを
            oclUtilsは "\ NVIDIA GPU Computing SDK 4.2 \ OpenCL \ common"にあります。

"oclUtils_vs2005.sln"
"oclUtils_vs2008.sln"
"oclUtils_vs2010.sln"

           - SDKサンプルのリリース版はoclUtils [32 | 64] .libにリンクしています。デバッグバージョン
            これらのサンプルのうちoclUtils [32D | 64D] .libにリンクします。

           - oclUtilsコンパイルの出力は、プロジェクト設定で設定されます。
            "NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ common \ lib"：

           - oclUtilsは、便宜上、このSDKで提供され、使用されています。それは必要ない
            独立したOpenCLアプリケーション開発。

9.手順6を実行した後で作成したサンプルアプリケーションを表示するには、リリースからサンプルを実行します
   または「NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ bin \ win [32 | 64] \ [release | debug]」にあるデバッグディレクトリを使用します。

     - すべてのSDKアプリケーションは、コンソールウィンドウから関心のあるメッセージをコンソールウィンドウに出力します。
      基本的なOpenCLプログラムの流れを理解し、いくつかのアプリケーションが生成する立場
      グラフィックスは別のOpenGLウィンドウで出力されます。
      
     - 多くのSDKアプリケーションでは、
      プログラムの構造とフローの全体的な見通しとセットアップに必要な時間と
重要な機能の実行。しかし、SDKのサンプルコードは、
教育目的のために簡素化されており、最適化されていません。高度な最適化
技術はこのSDKの範囲を超えています。
サンプルはベンチマークのような使用を意図したものではありません。

     - すべてのアプリケーションは、すべてのコンソール情報をセッションログファイルに
      実行可能ファイルと同じディレクトリ。これらのファイルの名前は、サンプルアプリケーションの名前の後ろに明示的に付けられています。
      拡張子は.txtです。

     - 便宜上、oclSDK.batバッチファイルは、実行可能ディレクトリにa
ビルドされたソリューションファイルからビルド後のイベント：

"oclRelease_vs2005.sln"
"oclRelease_vs2008.sln"
"oclRelease_vs2010.sln"

このバッチファイルを実行すると、各サンプルの完了時に実行が一時停止するだけで、
上記のように各アプリケーションによって生成されたログファイルは、ユーザーの
すべてのサンプルが完了した後で（数分）便利です。 oclSDK.batファイルも作成します。
すべての出力の完全なシーケンスを含む統合ログファイル "oclSDK.txt"
サンプルはoclSDK.batによって実行されます。

10.シンタックスハイライト
10。

Visual Studio 2005（VC8）、Visual Stuido 2008（VC9）の構文ハイライトファイル
    このSDKは「NVIDIA GPU Computing SDK 4.2 \ OpenCL \ doc \ usertype.dat」に付属しています。このファイル
OpenCL APIデータ型が含まれています。このファイルを適切なディレクトリに追加する（または
Visual Studioを起動する前に、このファイルの既存のコピーに内容をコピーします）。
OpenCL固有のデータ型の強調表示を提供します。
   
    32ビットWindows上のVS 8とVS 9のusertype.datファイルのデフォルトの場所は次のとおりです
        C：\ Program Files \ Microsoft Visual Studio 8 \ Common7 \ IDEまたは
        C：\ Program Files \ Microsoft Visual Studio 9 \ Common7 \ IDE

    64ビットWindows上のVS 8とVS 9用のusertype.datファイルのデフォルトの場所は次のとおりです
        C：\ Program Files（x86）\ Microsoft Visual Studio 8 \ Common7 \ IDEまたは
        C：\ Program Files（x86）\ Microsoft Visual Studio 9 \ Common7 \ IDE

    詳細については、NVIDIA OpenCLスタートガイドの第4章を参照してください。

-----------------------------
-------------------------------------------------- ------------------------------
II.B. Linuxのインストール手順
-------------------------------------------------- ------------------------------
1. NVIDIA GPU Computing SDKのOpenCL SDKサンプルには、CUDA ComputeでGPUが必要です
     適切に動作するアーキテクチャ。 CUDAアーキテクチャコンピューティング対応GPUの完全なリストについては、
     オンラインのリストを参照してください：http://www.nvidia.com/object/cuda_learn_products.html

2. NVIDIA GPU Computing SDKのOpenCLアプリケーションには、NVIDIAのバージョン258.19が必要です
   32ビットまたは64ビットのLinuxで実行するには、Display Driver以降が必要です。この必要なドライバは、
   登録された開発者はhttps://nvdeveloper.nvidia.com/login.asp?action=login
   
   ドライバインストールのヒントドキュメントを必ずお読みください
   ドライバをインストールします。http://www.nvidia.com/object/driver_installation_hints.html

3.以前のバージョンのNVIDIA GPU Computing SDKをアンインストールします。

4.ご使用のOSに付属のインストーラを実行して、NVIDIA GPU Computing SDKをインストールします。
             
   OpenCL SDKのデフォルトのインストールフォルダは次のとおりです。

     Linux
           $（HOME）/ NVIDIA_GPU_Computing_SDK /
           
     以下では、SDKがインストールされているパスを<NV_COMPUTE_SDK_PATH>として参照します。
     
5. 32ビットまたは64ビットのビルド（インストールOSと一致）、リリースおよびデバッグ
   構成、SDKプロジェクトの全セットとユーティリティの依存関係
   a。 <NV_COMPUTE_SDK_PATH> / OpenCLに移動します。
   b。ビルド：
     - "make"とタイプして設定を解除する。
     - "make dbg = 1"と入力して設定をデバッグします。

   トップレベルでmakeを実行すると、まず共有ライブラリと共通ユーティリティライブラリがビルドされます。
   SDKサンプル（これらのライブラリは便宜上のものであり、OpenCLの一部ではありません
   あなた自身のOpenCLプログラムでは必要ありません）。 Makeはそれぞれをビルドします
   SDKのプロジェクトの

6.次の場所にあるreleaseまたはdebugディレクトリからサンプルを実行します。
   <NV_COMPUTE_SDK_PATH> / OpenCL / bin / linux / [リリース|デバッグ]。

     - ほとんどのSDKアプリケーションは、コンソールウィンドウから関心のあるメッセージをコンソールウィンドウに出力します。
      基本的なOpenCLプログラムの流れを理解し、いくつかのアプリケーションが生成する立場
      グラフィックスは別のOpenGLウィンドウで出力されます。
      
     - 多くのSDKアプリケーションでは、
      プログラムの構造とフローの全体的な視点と、セットアップと実行に必要な時間
      重要な機能。しかし、SDKのサンプルコードは、一般的に教授のために簡素化されています
      最適化されていません。高度な最適化手法は、このSDKの対象外です。
      サンプルによって提示される任意のタイミング情報は、ベンチマークのような使用のためのものではありません。

     - すべてのアプリケーションは、すべてのコンソール情報をセッションログファイルに
      実行可能ファイルと同じディレクトリ。これらのファイルの名前は、サンプルアプリケーションの名前の後ろに明示的に付けられています。
      拡張子は.txtです。

     - 便宜上、<NV_COMPUTE_SDK_PATH> / OpenCLのMakefileを使用して、すべてを実行することができます
      SDKは、「make runall」または「make dbg = 1 runall」と入力して順番にサンプリングします。

-------------------------------
-------------------------------------------------- ------------------------------
III.A. SDKインフラストラクチャを使用してWindowsで新しいOpenCLプログラムを作成する
-------------------------------------------------- ------------------------------

NVIDIA OpenCL SDKインフラストラクチャを使用して新しいOpenCLプログラムを作成するのは簡単です。
次の手順に従ってください：

1.インストールされているOpenCL SDKプロジェクトフォルダの1つをその全体にコピーします。
   "\ NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ src"に移動し、フォルダの名前を変更します。今あなたは持っている
   「\ NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ src \ <myproject>」のようなフォルダ

2.必要に応じてプロジェクトのファイル名を編集します。

3. * .sln、* .vcproj、およびソースファイルを編集します。すべて検索と置換
   あなたが選んだ新しいファイル名への古いファイル名の出現。

4.以下を使用して、32ビットおよび/または64ビットのリリースおよびデバッグ構成をビルドします。
      <myproject> _vs2005.sln
<myproject> _vs2008.sln
<myproject> _vs2010.sln

5.リリースまたはデバッグの<myproject> .exeを実行します。
   "NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ bin \ win [32 | 64] \ [release | debug]"

6.必要な計算を実行するようにコードを変更します。 OpenCLを参照してください
   プログラミングガイド、OpenCL API仕様、およびOpenCLベストプラクティスガイド
   OpenCLでのプログラミングの詳細については、

--------------------------
-------------------------------------------------- ------------------------------
III.B. SDKインフラストラクチャを使用してLinux用に独自のOpenCLプログラムを作成する
-------------------------------------------------- ------------------------------

NVIDIA OpenCL SDKインフラストラクチャを使用して新しいOpenCLプログラムを作成するのは簡単です。
次の手順に従ってください：

1.インストールされているOpenCL SDKプロジェクトフォルダの1つをその全体にコピーします。
   "<NV_COMPUTE_SDK_PATH> / OpenCL / src"と入力し、フォルダの名前を変更します。今あなたは持っている
   "<NV_COMPUTE_SDK_PATH> / OpenCL / src / myproject"のようなフォルダは、

2.必要に応じてプロジェクトのファイル名を編集します。

3. Makefileを編集します。すべて検索と置換
   あなたが選んだ新しいファイル名への古いファイル名の出現。

4. 32ビットおよび/または64ビットのリリースおよびデバッグをビルドする
   "make"または "make dbg = 1"と入力して設定します。

5.リリースまたはデバッグのmyproject実行可能ファイルを実行します。
   "<NV_COMPUTE_SDK_PATH> / OpenCL / bin / linux / [リリース|デバッグ]"を選択します。

6.必要な計算を実行するようにコードを変更します。 OpenCLを参照してください
   OpenCLでのプログラミングの詳細については、「プログラミングガイド」および「OpenCL API仕様」を参照してください。

---------------------------------
-------------------------------------------------- ------------------------------
IV.A. WindowsでSDKインフラストラクチャの外に新しいOpenCLプログラムを作成する
-------------------------------------------------- ------------------------------

NVIDIA OpenCL SDKインフラストラクチャを使用せずに新しいOpenCLプログラムを作成するには、
主要なファイルは、見つけて活用するために重要です。

1. NVIDIAで動作するアプリケーションを構築するために必要な唯一のOpenCL固有のファイル
   サポートされているOSを搭載したシステム上でCUDAアーキテクチャのコンピューティング対応GPU
   OpenCLをサポートする推奨NVIDIAディスプレイドライバは次のとおりです。

    - ヘッダー：
        cl.h
        cl_platform.h
        cl_ext.h
        cl_gl.h
        cl_gl_ext.h
        cl_d3d11_ext.h
        cl_d3d10_ext.h
        cl_d3d9_ext.h
        opencl.h
        
        これらのファイルは、「NVIDIA GPU Computing SDK 4.2 \ OpenCL \ common \ inc \ CL」にあります。

    - スタブ・リブ
        OpenCL.lib（Win32およびx64プラットフォーム用の異なるファイル）

        この.libファイルは、OpenCLドライバ/コンパイラへのビルド時の暗黙的なリンク用です。
        OpenCL.dllであり、それらは次の場所にあります。
        
        "NVIDIA GPUコンピューティングSDK 4.2 \ OpenCL \ common \ lib \ [Win32 | x64]
            
        注：これらのlibファイルは、実行時に明示的なDLLリンケージを実装するアプリケーションには必要ありません。

-------------------------------------------------- ------------------------------
IV.B. Linux用の独自のOpenCLプログラムをSDKインフラストラクチャの外に作成する
-------------------------------------------------- ------------------------------

NVIDIA OpenCL SDKインフラストラクチャを使用せずに新しいOpenCLプログラムを作成するには、
主要なファイルは、見つけて活用するために重要です。

1. NVIDIAで動作するアプリケーションを構築するために必要なOpenCL固有のファイル
   サポートされているOSを搭載したシステム上でCUDAアーキテクチャのコンピューティング対応GPU
   OpenCLをサポートする推奨NVIDIAディスプレイドライバは次のとおりです。

    - ヘッダー：
        cl.h
        cl_platform.h
        cl_ext.h
        cl_gl.h
        cl_gl_ext.h
        opencl.h

        これらのファイルは、「NVIDIA GPU Computing SDK 4.2 \ OpenCL \ common \ inc \ CL」にあります。
    
---------------------
-------------------------------------------------- ------------------------------
V.（a）Mac OSXの既知の問題
-------------------------------------------------- ------------------------------
1. Mac OSX SnowLeopard（10.6）では、次の3つのSDKサンプルはOpenCL SDKパッケージに含まれていません。
   これらのサンプルは現在、OSX SnowLeopardで動作していません。これらの問題を解決するために取り組んでいます。
 
    - oclFDTD3D
    - oclQuasirandomGenerator
    - oclSimpleConvolution
      
2.このアップデートされたSDK（OpenCL 1.0リリース）のリリース日現在、OpenCLサポートとの不一致
   Mac OSX上でビルドや実行の失敗が発生する可能性があります。付属のSDKおよびOpenCLバイナリ
   258.19ドライバーは、2010年6月10日に公開されたKhronosの最新ヘッダーを使用しています。
   更新されたNVIDIA拡張ヘッダー。しかし、Mac OSX上のOpenCLサポートのシンボルは、
   OpenCL.framework、およびMac OSXで現在サポートされているOpenCLのリビジョンのヘッダファイルは
   Apple、Inc.から配布されています。OpenCLのMac OSXサポートに関する情報は、
         
http://developer.apple.com/mac/library/documentation/Performance/Conceptual/OpenCL_MacProgGuide/Introduction/Introduction.html

-------------------------------------------------- ------------------------------
V.（b）Linuxでの既知の問題
-------------------------------------------------- ------------------------------
-------------------------------------------------- ------------------------------
V.（b）Linuxでの既知の問題
-------------------------------------------------- ------------------------------

1. OpenGLを使用するSDKサンプルはビルドやリンクに失敗します。これは、デフォルトの多く
       多くのLinuxディストリビューションのインストールには、必要なOpenGL、GLUT、GLU、GLEW、
X11、Xi、Xlib、またはXmiヘッダーまたはライブラリ。一般的で具体的な解決策は次のとおりです。

       （a）Redhat 4 Linuxディストリビューション
"ld：-lglutを見つけることができません"。いくつかのLinuxインストールで、oclSimpleGLの例をビルドする
以下のようなリンクエラーが表示されます。

/ usr / bin / ld：-lglutが見つかりません

通常、これは、SDKのmakefileがlibglut.soを検索し、
それの亜種（libglut.so.3のようなもの）。これが問題であることを確認するには、単純に
次のコマンドを実行します。

ls / usr / lib |グレープグート

ls / usr / lib64 |グレープグート

次の（または類似の）出力が表示されます。

lrwxrwxrwx 1ルートルート16 Jan 9 14:06 libglut.so.3 - > libglut.so.3.8.0
-rwxr-xr-x 1ルートルート164584 2004/08/14 libglut.so.3.8.0

/ usr / libおよび/または/ usr / lib64にlibglut.so.3がある場合は、単に次のコマンドを実行してください
ルートとして

ln -s /usr/lib/libglut.so.3 /usr/lib/libglut.so
ln -s /usr/lib64/libglut.so.3 /usr/lib64/libglut.so

libglut.so.3を持っていない場合は、glutパッケージ
RHELシステムに次のコマンドでインストールします。

rpm -qa |グレープグート

あなたは "freeglut-2.2.2-14"または同様の出力を見るべきです。そうでない場合、あなたは
システム管理者が "freeglut-2.2.2-14"パッケージをインストールする必要があります。
手順については、Red Hatおよび/またはrpmのマニュアルを参照してください。

libglut.so.3を持っていても、/ usr / libへの書き込みアクセス権がない場合は、
この問題を解決するには、ディレクトリにソフトリンクを作成します。
書き込み権限があり、そのディレクトリをライブラリに追加します
検索パス（-L）はMakefileにあります。
        
（b）Linuxディストリビューション（RedhatやFedoraなど）にはGLUライブラリが含まれていないものがあります。
最新のパッケージは、このWebサイトからダウンロードできます。お願いします
正しいLinuxディストリビューションに一致することを確認してください。

http：//fr.rpmfind.net/linux/rpm2html/search.php？query = libGLU.so.1＆submit = Search + ...

        （c）（SLED11）SUSE Linux Enterprise Edition 11がありません：
"libGLU"、 "libX11"、 "libXi"、 "libXm"

この特定のバージョンのSUSE Linux 11には、次のライブラリのシンボリックリンクがありません。

私。 libGLU

ls / usr / lib | grep GLU
ls / usr / lib64 | grep GLU

libGLU.so.1
libGLU.so.1.3.0370300

適切なシンボリックリンク（32ビットおよび64ビットOS）を作成するには、

ln -s /usr/lib/libGLU.so.1 /usr/lib/libGLU.so
ln -s /usr/lib64/libGLU.so.1 /usr/lib64/libGLU.so

ii。 libX11

ls / usr / lib | grep X11
ls / usr / lib64 | grep X11
 
libX11.so.6
libX11.so.6.2.0

適切なシンボリックリンク（32ビットおよび64ビットOS）を作成するには、

ln -s /usr/lib/libX11.so.6 /usr/lib/libX11.so
ln -s /usr/lib64/libX11.so.6 /usr/lib64/libX11.so

iii。 libXi

ls / usr / lib | grep Xi
ls / usr / lib64 | grep Xi

libXi.so.6
libXi.so.6.0.0

適切なシンボリックリンク（32ビットおよび64ビットOS）を作成するには、

ln -s /usr/lib/libXi.so.6 /usr/lib/libXi.so
ln -s /usr/lib64/libXi.so.6 /usr/lib64/libXi.so

iv。 libXm

ls / usr / lib | grep Xm
ls / usr / lib64 | grep Xm

libXm.so.6
libXm.so.6.0.0

適切なシンボリックリンク（32ビットおよび64ビットOS）を作成するには、

ln -s /usr/lib/libXm.so.6 /usr/lib/libXm.so
ln -s /usr/lib64/libXm.so.6 /usr/lib64/libXm.so


（d）Ubuntu LinuxがOpenGLを使用するこれらのSDKサンプルをビルドできない

デフォルトのUbuntuディストリビューションに多数のライブラリがありません

私。欠けているのは、GLUT、Xi、Xmu、GL、およびX11ヘッダーです。これらのヘッダーを追加するには
ライブラリを配布するには、コマンドラインで次のように入力します。
 
sudo apt-get install freeglut3-devビルドに不可欠なlibx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev

            ii。 Mesaをインストールすると、libGLに対するリンクエラーが表示されることに注意してください。これは以下のように解決できます：

            cd / usr / lib /
            sudo rm libGL.so
            sudo ln -s libGL.so.1 libGL.so


-----------------------------------
-------------------------------------------------- ------------------------------
VI。 よくある質問
-------------------------------------------------- ------------------------------

NDAやその他の早期アクセスプログラムに参加している開発者は、
質問、コメントなどをopencl@nvidia.comに送ってください。
第三者との経験

公式OpenCL FAQは、NVIDIA OpenCLフォーラムでオンラインで入手できます：

     http://forums.nvidia.com/index.php?showforum=134

-------------------------------------------------- ------------------------------
VII。 変更ログ（最初にリストされた最新の変更）
-------------------------------------------------- ------------------------------
-------------------------------------------------- ------------------------------
VII。変更ログ（最初にリストされた最新の変更）
-------------------------------------------------- ------------------------------
OpenCL R295およびR300が更新されました
Kepler GPUアーキテクチャのドライバサポート。

OpenCL R285 RC1アップデート
* oclMultiThreads - 新しいイベントとコールバック関数を使用する方法を示すOpenCL SDKのサンプルを追加しました。
  デフォルトでは、oclRelease_vs2005.slnにはoclMultiThreadsのソリューションファイルが含まれていないことに注意してください。
  VS2005でこのsampkeをビルドするには、Microsoft SDK v6.0以降をインストールする必要があります。 VS2008およびVS2010
  プロジェクトはこのサンプルに含まれています。

OpenCL R280アップデート
* OpenCL 1.1のサポートを追加

OpenCL R270アップデート
* OpenCL SDKサンプルのVS2010プロジェクトサポートが追加され、SDKサンプルがVisual Studio 2010でビルドされるようになりました
*追加されたSDKサンプル：oclInlinePTX - OpenCLカーネル内にPTXを埋め込む方法を示す
* VS2005、VS2008、VS2010のOpenCL個別SDKサンプルソリューションファイル（* .sln）が更新されました。
  個々のソリューションには、SDKヘルパーライブラリによるプロジェクトの依存関係が含まれています。 SDKサンプル
  shrUtilsやoclUtilsとのリンクに依存するため、個々のOpenCL SDKサンプルをビルドできるようになりました
  その依存関係を構築するためにoclRelease_vs20 ??。slnを使用することはありません。

OpenCL R260リリース
* SDKサンプルの追加：oclMarchingCubes

OpenCL R260ベータリリース候補
*追加されたSDKサンプル：oclTridiagonal

OpenCL 1.0リリース
* SDKサンプルを追加：oclSimpleD3D9Texture、oclSimpleD3D10Texture
* 258.19ドライバの修正により、oclCopyComputeOverlapの回避策が削除されました。
*その他のクリーンアップ、バグ修正と改善

OpenCL R256 Beta
* SDKサンプルを追加：oclHiddenMarkovModel、oclSimpleD3D9Texture、oclSimpleD3D10Texture
*マイナークリーンアップと改善

OpenCL R195リリース
* KhronosのすべてのOpenCLヘッダが更新されました
* NVIDIA OpenCL拡張ヘッダーが更新され、4つが新たに追加されました
（cl_gl_ext.h、cl_d3d11_ext.h、cl_d3d10_ext.h、cl_d3d9_ext.h）
* ICD、CL-GL interopおよびCL-D3D interopのサポート
http://www.khronos.org/registry/cl/
* OpenGLとOpenCLの両方を使用している一部のSDKサンプルは、新しいCL-GL interopを使用するように更新されました
* oclCopyComputeOverlapを追加しました
   - OpenCLでコピーとカーネルの実行を処理する方法を示す
*バグの修正と改善
*更新されたドキュメント

OpenCL R195アップデートリリース
*更新された/改善されたドライバと組み合わせたその他のSDKソースコードの改良
* Khronos OpenCL仕様とクイックリファレンスカードを最新版にアップデート
* clext.hファイル名がcl_ext.hに変更されました。
* cl_ext.h内の拡張の列挙名が更新されました
* OpenCL.libは、OpenCL.dll（ドライバーで別途に配布）の変更を__cdeclから__stdcallに変更するために更新されました
*以前のNVIDIA OpenCLドライバは、開発者がNULLまたはデフォルトのプラットフォーム、
  clCreateContextと関連するコールに渡されるように、NVIDIAのプラットフォームでした。このアプローチは互換性がありません
  単一のプラットフォーム上で複数のベンダーをサポートしています（どのベンダーがデフォルトであるかは不明です）。
  将来のマルチベンダーOpenCLインストールとの互換性を準備するために、NVIDIAのドライバはもはや
  プラットフォームとしてNULLを守ります。これには、OpenCLプログラムを明示的に変更する必要があります。
  適切なベンダーを選択してください。この変更はサンプルコードに反映されています
  このSDKリリースでは

OpenCL R190アップデートリリース
* OpenCLコンパイラ/ドライバをSDKからr190 GPUドライバに移行
* OpenCLコンパイラ/ドライバには、さまざまな修正、拡張機能、およびパフォーマンスの改善が含まれています。
*更新されたOpenCLヘッダーとライブラリ
*必須/付属のr190ドライバはCUDA 2.3と互換性があります
*追加：Windows 7（32ビットおよび64ビット）のサポート
Win32ターゲット用の32ビットWindows SDKパッケージを統一しました。 （32ビットWindows XP、Vista、Win7）= 1 SDKインストーラパッケージ
* x64ターゲット用の64ビットWindows SDKパッケージを統一しました。 （64ビットWindows XP、Vista、Win7）= 1 SDKインストーラパッケージ
*クロスコンパイル（32/64および64/32）は、OpenCLサンプルプロジェクトで動作するようになりました。
* SDKバージョン4788711
  いくつかのサンプルでのマルチGPUサポートを含むSDKサンプルコードの多数のリビジョン
  追加されたサンプル：oclMedianFilter、oclFDTD3d、oclRadixSort、
                  oclMersenneTwister、oclSemirandomGenerator、
                  oclMatVecMul、oclHiddenMarkovModel
* SDKサンプルはMac OSX SnowLeopardをサポートしていますが、いくつかは除外されています。 「既知の問題」を参照してください。
* OpenCLベストプラクティスガイドの追加
* OpenCLプログラミングの概要の追加
* WindowsおよびLinux用統合リリースノート1セット
*その他のドキュメントの更新

OpenCL 1.0準拠リリース
* SDKコンテンツのマイナーリビジョンとoclSobelFilterサンプルの追加、SDK 1.00.00.07
* OpenCL適合

OpenCL 1.0 Beta 1.2
* SDKコンテンツのマイナーリビジョン、SDK 1.00.00.06
* Khronosから新しいOpenCL仕様（v1.00.43）をバンドル

OpenCL 1.0 Beta 1.1
* Vista32およびVista64 OpenCLプレリリースバイナリを他のプラットフォームと同等のバージョンに改訂
*更新されたVista 32および64を反映したSDKコンテンツのマイナーリビジョン
OpenCL 1.0 Beta 1.1
* Vista32およびVista64 OpenCLプレリリースバイナリを他のプラットフォームと同等のバージョンに改訂
*更新されたVista 32および64 OpenCLバイナリ、SDK 1.00.00.05を反映したSDKコンテンツのマイナーリビジョン

OpenCL 1.0 Beta 1
* WinXP 32、WinXP64、Linux 32＆64（カーネルバージョン2.6）、WinVista 32、WinVista 64をサポート
*パブリックWHQLドライバ185.85（Win）と185.18.08（Linux）にGPUディスプレイドライバを更新
  （GPUドライバは現在、CUDA 2.2およびOpenCLと互換性があります）
WinXP 32＆64およびLinux 32＆64の以前の既知の問題の解消
*その他その他のアップデートと改善、SDK 1.00.00.04

OpenCL 1.0準拠候補リリース
* WinXP 32およびLinux 32（Kernel Version 2.6）がサポートされています。
*パブリックWHQLドライバ185.85（Win）と185.18.08（Linux）にGPUディスプレイドライバを更新
  （GPUドライバは現在、CUDA 2.2およびOpenCLと互換性があります）
WinXP 32およびLinux 32の以前の既知の問題の削除
*その他その他の更新と改善

リリース1.0のAlpha 2.1
* 64ビットWinXP、WinVista、Linux（Ubuntu 8.1）のサポートを追加。
*その他更新と改善

リリース1.0 Alpha 2 Windows Driver Refresh
*新しいWindows GPUドライバのアップデート、その他の修正、追加、解説

リリース1.0のアルファ2
*最初の開発者 - パートナーNDAリリース

-------------------------------------------------- ------------------------------
VIII。 OSプラットフォームとコンパイラのサポート
-------------------------------------------------- ------------------------------
-------------------------------------------------- ------------------------------
VIII。 OSプラットフォームとコンパイラのサポート
-------------------------------------------------- ------------------------------

[Windowsプラットフォーム]
CUDA 4.2によるOSプラットフォームのサポート
* KeplerベースのGPUのサポート

CUDA 4.1によるOSプラットフォームのサポート
*変更なし

CUDA 4.0によるOSプラットフォームのサポート
*新しいコンパイラのサポート
o Visual Studio 10（2010）
*サポートされているコンパイラ
o Visual Studio 9（2008）
o Visual Studio 8（2005）
*サポートされているOS
Windows XP、Windows Vista、Windows 7
Windows Server 2008および2008 R2

OSプラットフォームのサポートがCUDA 3.0リリースに追加されました
* Windows 7 32＆64
* Windows Server 2008および2008 R2

OSプラットフォームのサポートがCUDA 2.2に追加されました
* Vista 32＆64ビット、WinXP 32＆64ビット
o Visual Studio 9（2008）
o Visual Studio 8（2005）

[Macプラットフォーム]
CUDA 4.2によるOSプラットフォームのサポート
* KeplerベースのGPUのサポート

CUDA 4.1によるOSプラットフォームのサポート
*変更なし

CUDA 4.0によるOSプラットフォームのサポート
*新しいOSプラットフォームが追加されました
MacOS X Lion 10.7.x
*継続OSプラットフォーム
MacOS X SnowLeopard 10.6.x

OSプラットフォームのサポートがCUDA 3.2に追加されました
* MacOS X SnowLeopard 10.6.5
* MacOS X SnowLeopard 10.6.4

OSプラットフォームのサポートがCUDA 3.1 Betaに追加されました
* MacOS X SnowLeopard 10.6.3

OSプラットフォームのサポートがCUDA 3.0リリースに追加されました
* MacOS X SnowLeopard 10.6.x

OSプラットフォームのサポートがCUDA 3.0 Beta 1に追加されました
* MacOS X SnowLeopard 10.6（32ビット）


[Linuxプラットフォーム]
CUDA 4.2によるOSプラットフォームのサポート
* KeplerベースのGPUのサポート

CUDA 4.1によるOSプラットフォームのサポート
*新しいOSプラットフォームが追加されました
Ubuntu 11.04、
Fedora 14、
RHEL-5.5、5.6、5.7（32ビットおよび64ビット）
RHEL-6.X（6.0,6.1）（64ビットのみ）、
ICCコンパイラ11.1（32ビットおよび64ビットLinux）
*継続OSプラットフォーム
SLES 11.1、
Ubuntu 10.04、
OpenSUSE-11.2
*サポートされなくなったプラットフォーム
Ubuntu 10.10、
Fedora 13、
RHEL-4.8

CUDA 4.0によるOSプラットフォームのサポート
*新しいOSプラットフォームが追加されました
SLES11-SP1、
RHEL-6.0（64ビットのみ）、
Ubuntu 10.10
*継続OSプラットフォーム
OpenSUSE-11.2
Fedora 13、
RHEL-4.8（64ビットのみ）、
RHEL-5.5
*サポートされなくなったプラットフォーム
RHEL-4.8（32ビットのみ）
Ubuntu 10.04、
SLED11-SP1

OSプラットフォームのサポートがCUDA 3.2に追加されました
*追加プラットフォームのサポートLinux 32＆64：
Fedora 13、
Ubuntu 10.04、
RHEL-5.5、
SLED-11SP1、
ICC（64ビットLinuxのみ？）
*サポートされなくなったプラットフォーム
Fedora 12、
Ubuntu 9.10
RHEL-5.4、
SLED11

OSプラットフォームのサポートがCUDA 3.1に追加されました
*追加プラットフォームのサポートLinux 32＆64：
Fedora 12、
OpenSUSE-11.2、
Ubuntu 9.10
RHEL-5.4
*サポートされなくなったプラットフォーム
Fedora 10、
OpenSUSE-11.1、
Ubuntu 9.04

OSプラットフォームのサポートがCUDA 3.0に追加されました
* Linuxディストリビューション32＆64：
RHEL-4.x（4.8）、
RHEL-5.x（5.3）、
SLED-11
Fedora10、
Ubuntu 9.04、
OpenSUSE 11.1
o gcc 3.4、gcc 4


--------------------------------------------------------------------------------
日本語翻訳　おわり

--------------------------------------------------------------------------------
NVIDIA GPU Computing Software Development Kit
OpenCL SDK 4.2 Release Notes
R295 and R300 Release Driver

  Windows XP, Windows Vista, and Windows 7 (32/64-bit)
  Windows Server 2003, 2003 R2, 2008, 2008 R2
  Linux OS (32/64-bit)
  Mac OSX  (10.6.x SnowLeopard 32/64-bit, 10.7.x Lion 32/64-bit)

--------------------------------------------------------------------------------
--------------------------------------------------------------------------------

--------------------------------------------------------------------------------
TABLE OF CONTENTS
--------------------------------------------------------------------------------
I      Legal Notice
II  A  Windows Installation Instructions
II  B  Linux Installation Instructions
III A  Creating Your Own OpenCL Program for Windows using the SDK infrastructure
III B  Creating Your Own OpenCL Program for Linux using the SDK infrastructure
IV  A  Creating Your Own OpenCL Program for Windows outside of the SDK infrastructure
IV  B  Creating Your Own OpenCL Program for Linux outside of the SDK infrastructure
V.  A  Known Issues on Mac OSX
V.  B  Known Issues on Linux
VI.    Frequently Asked Questions
VII.   Change Log
VIII.  OS Platforms and Compilers Supported
--------------------------------------------------------------------------------

--------------------------------------------------------------------------------
I.   Legal Notice
--------------------------------------------------------------------------------
NOTICE:  This release is made available to you under the terms and conditions of the 
end user license agreement (EULA) distributed with this release.  If you do not accept 
the EULA, you do not have rights to use the files included in this release and must 
delete all copies of all files associated with this release immediately.

--------------------------------------------------------------------------------
II.A.   Windows Installation Instructions
--------------------------------------------------------------------------------

1. OpenCL SDK samples included with NVIDIA GPU Computing SDK require a GPU with CUDA Compute 
   Architecture to run properly. For a complete list of CUDA-Architecture compute-enabled GPUs, 
   see the list online at:  http://www.nvidia.com/object/cuda_learn_products.html

2. OpenCL SDK samples in the NVIDIA GPU Computing SDK require version 295.xx or 300.xx of the NVIDIA 
   Display Driver or later to run on 32 bit or 64 bit Windows XP, Windows Vista or Windows 7.  
   This required driver is available pubically through this link.

   http://www.nvidia.com/Download/index.aspx?lang=en-us
   
   Please make sure to read the Driver Installation Hints Document before you 
   install the driver: http://www.nvidia.com/object/driver_installation_hints.html

       To download the NVIDIA Drivers refer to this link
       
       http://www.nvidia.com/page/pg_20030521269172.html
   
3. This SDK includes OpenCL/DirectX interop SDK samples that depend on the Microsoft DirectX SDK.  
   In order to build these samples, please download the Microsoft DirectX SDK from June 2010 or 
   newer from this link.
       
       http://msdn.microsoft.com/en-us/directx/default.aspx
   
4. Uninstall any previous versions of the NVIDIA GPU Computing SDK

5. Install the NVIDIA GPU Computing SDK by running the installer provided for your OS.
    
   The default installation folder for the OpenCL SDK is: 

   Windows XP
       C:\Documents and Settings\All Users\Application Data\NVIDIA Corporation\NVIDIA GPU Computing SDK 4.2\OpenCL

   Windows Vista
       C:\ProgramData\NVIDIA Corporation\NVIDIA GPU Computing SDK 4.2\OpenCL
           
   Note: The "Application Data" and "ProgramData" folders maybe hidden as default in "Windows Explorer"
          on many Windows installations.  They can be made visible in "Windows Explorer" if desired.
          To do this, change the settings in "Folder Options" in the "Tools" menu in the Windows File
		  Explorer.
      
6. After installing the SDK, open the SDK Browser from the Start Menu by clicking on "NVIDIA GPU Computing 
   SDK Browser" in the NVIDIA GPU Computing folder within the NVIDIA Corporation program group 
   installed in the Windows Start Menu.  

      - Each installed SDK sample program is shown along with links for running the executable and 
        viewing the source code files.
 
      - Some of the samples additionally present a link to a Whitepaper describing the sample in detail.
 
      - The samples are presented within the SDK browser in approximate order of complexity, from the least 
        complex projects at the top to the most complex projects at the bottom.

7. Build the 32-bit or 64-bit (match the installation OS), release and debug  
   configurations, of the entire set of SDK projects and utility dependencies using 
   the provided solutions:

      "oclRelease_vs2005.sln" for Visual Studio 2005 (VC8)
	  "oclRelease_vs2008.sln" for Visual Studio 2008 (VC9)
	  "oclRelease_vs2010.sln" for Visual Studio 2010 (VC10)
	  
   These .sln files are installed into the "\NVIDIA GPU Computing SDK 4.2\OpenCL" directory 
   of the SDK. They will build or copy all SDK sample executables (*.exe) and relevant (*.lib) and (*.dll) 
   for the present OS and place execution binaries in the proper directories within   
   "\NVIDIA GPU Computing SDK 4.2\OpenCL\bin\<platform>\<configuration>" 
   
   For subsequent builds, you can either 
      - Use the individual solution files located in each of the examples' directories in 
        "NVIDIA GPU Computing SDK 4.2\OpenCL\src", or
        
      - Use the global solution files located in "\NVIDIA GPU Computing SDK 4.2\OpenCL".
		  "oclRelease_vs2005.sln"
		  "oclRelease_vs2008.sln"
		  "oclRelease_vs2010.sln"
   
8. Build Structure Notes for the OpenCL portion of the NVIDIA GPU Computing SDK:
      
      - "$(PlatformName)" (VS2005/VS2008) or "$(Platform)" (VS2010) is used by the Visual Studio 
	    projects in the SDK to switch to the correct OpenCL.lib file version (Win32 or x64) in the 
		"NVIDIA GPU Computing SDK 4.2\OpenCL\lib" folder.  This is a stublib file needed at build 
		time for implicit linking to the OpenCL dll's, which are installed on the system with the 
		proper NVIDIA GPU driver.
        
      - A post-build event is executed after building:
			  "oclRelease_vs2005.sln",
			  "oclRelease_vs2008.sln",
			  "oclRelease_vs2010.sln"
		and 
			  "oclUtils_vs2005.sln",
			  "oclUtils_vs2008.sln",
			  "oclUtils_vs2010.sln"
				  
		  causing necessary dll's to be copied to the directory within 
		  "NVIDIA GPU Computing SDK 4.2\OpenCL\bin\<platform>\<configuration>" 
		  
        (the same directory containing the *.exe files, as also discussed in item 6 above). This puts 
        the DLL's in the first default path location searched by Windows upon execution. 

      - The samples in the NVIDIA GPU Computing SDK link statically to a utility library called 
        "shrUtils" which is a set of generic C++ utilities unrelated to OpenCL but useful for 
        making sample demonstration applications with any of the NVIDIA GPU Computing API's. 

          - Developers need not worry about shrUtils if step #6 above is executed, because this dependency 
            is taken care of in step #6. But developers may review or edit source code for shrUtils using
			solution files in "\NVIDIA GPU Computing SDK 4.2\shared\":
			
            "shrUtils_vs2005.sln"
			"shrUtils_vs2008.sln"
			"shrUtils_vs2010.sln"
        
          - The release version of SDK samples link to shrUtils[32|64].lib. The debug versions 
            of these samples link to shrUtils[32D|64D].lib .
            
          - The output of the shrUtils_vs2005/08/10.sln compilation is set in project settings to go to the 
            subdirectory "NVIDIA GPU Computing SDK 4.2\shared\lib".
            
          - shrUtils is provided and used in this SDK for convenience only.  It is not necessary for
            independent OpenCL application development.

      - The OpenCL samples in the NVIDIA GPU Computing SDK also link statically to a utility library called 
        "oclUtils" which is a set of OpenCL related or OpenCL SDK specific utilities and also serves as a common 
        header for most standard system includes and shrUtils.
        
          - Developers need not worry about oclUtils if step #6 above is executed, because this dependency 
            is taken care of in step #6.  But developers may review or edit source code for oclUtils using 
            oclUtils is found under "\NVIDIA GPU Computing SDK 4.2\OpenCL\common". 
			
			   "oclUtils_vs2005.sln"
			   "oclUtils_vs2008.sln"
			   "oclUtils_vs2010.sln"

          - The release version of SDK samples link to oclUtils[32|64].lib. The debug versions 
            of these samples link to oclUtils[32D|64D].lib .

          - The output of the oclUtils compilation is set in project settings to go to
            "NVIDIA GPU Computing SDK 4.2\OpenCL\common\lib":

          - oclUtils is provided and used in this SDK for convenience only.  It is not necessary for
            independent OpenCL application development.

9. To view the as-built sample applications after executing step 6, run the examples from the release 
   or debug directories located in: "NVIDIA GPU Computing SDK 4.2\OpenCL\bin\win[32|64]\[release|debug]".

    - All of the SDK applications output messages to a console window that are of interest from the 
      standpoint of understanding basic OpenCL program flow, and several of the applications generate
      graphics output in a separate OpenGL window.  
      
    - Many of the SDK applications present some timing information useful for obtaining an 
      overall perspective of program structure and flow and the time required for setup and 
	  execution of significant functions.  The SDK example code, however, has generally been 
	  simplified for instructional purposes and is not optimized.  Advanced optimization 
	  techniques are beyond the scope of this SDK, and any timing information presented by 
	  the samples is not intended for such usage as benchmarking.  

    - All of the applications additionally log all the console information to a session log file in the
      same directory as the executables.  Those files are named clearly after the name of the sample app, 
      but with a .txt extension.  

    - For convenience, the oclSDK.bat batch file is placed in the executable directory by a 
	  post-build event from built solution files:
	  
			"oclRelease_vs2005.sln"
			"oclRelease_vs2008.sln"
			"oclRelease_vs2010.sln"
	  
	  When running this batch file, execution pauses only briefly at the completion of each sample, 
	  but the log files generated by each application (as noted above) may be viewed at the user's
	  convenience after all samples have completed (a few minutes).  The oclSDK.bat file also creates 
	  the integrated log file "oclSDK.txt" which contains the complete sequence of outputs for all 
	  samples run by oclSDK.bat.

10. A syntax highlighting file for Visual Studio 2005 (VC8), Visual Stuido 2008 (VC9) has been 
    provided with this SDK in "NVIDIA GPU Computing SDK 4.2\OpenCL\doc\usertype.dat".  This file 
	contains OpenCL API data types.  Adding this file to the proper directory (or pasting its 
	contents into any pre-existing copy of this file) prior to starting Visual Studio will 
	provide highlighting of the OpenCL specific data types.  
   
    The default location for the usertype.dat file for VS 8 and VS 9 on 32 bit Windows is
        C:\Program Files\Microsoft Visual Studio 8\Common7\IDE  or
        C:\Program Files\Microsoft Visual Studio 9\Common7\IDE  

    The default location for the usertype.dat file for VS 8 and VS 9 on 64 bit Windows is
        C:\Program Files (x86)\Microsoft Visual Studio 8\Common7\IDE  or
        C:\Program Files (x86)\Microsoft Visual Studio 9\Common7\IDE     

    See chapter 4 of the NVIDIA OpenCL Getting Started Guide for Windows for more information.

--------------------------------------------------------------------------------
II.B.   Linux Installation Instructions
--------------------------------------------------------------------------------

1. The OpenCL SDK samples in the NVIDIA GPU Computing SDK require a GPU with CUDA Compute 
     Architecture to run properly. For a complete list of CUDA-Architecture compute-enabled GPUs, 
     see the list online at:  http://www.nvidia.com/object/cuda_learn_products.html

2. The OpenCL applications in the NVIDIA GPU Computing SDK require version 258.19 of the NVIDIA 
   Display Driver or later to run on 32 bit or 64 bit Linux.  This required driver is made available to 
   registered developers at: https://nvdeveloper.nvidia.com/login.asp?action=login
   
   Please make sure to read the Driver Installation Hints Document before you 
   install the driver: http://www.nvidia.com/object/driver_installation_hints.html

3. Uninstall any previous versions of the NVIDIA GPU Computing SDK

4. Install the NVIDIA GPU Computing SDK by running the installer provided for your OS.
             
   The default installation folder for the OpenCL SDK is: 

     Linux
           $(HOME)/NVIDIA_GPU_Computing_SDK/  
           
     In the following we will refer to the path that the SDK is installed into as <NV_COMPUTE_SDK_PATH>.    
     
5. Build the 32-bit or 64-bit (match the installation OS), release and debug  
   configurations, of the entire set of SDK projects and utility dependencies.
   a. Go to <NV_COMPUTE_SDK_PATH>/OpenCL
   b. Build:
    - release configuration by typing "make".
    - debug   configuration by typing "make dbg=1".

   Running make at the top level first builds the shared and common utility libraries used by
   the SDK samples (these libraries are simply for convenience and are not part of the OpenCL
   distribution and are not required for your own OpenCL programs). Make then builds each
   of the projects in the SDK.    

6. Run the examples from the release or debug directory located in 
   <NV_COMPUTE_SDK_PATH>/OpenCL/bin/linux/[release|debug].

    - Most of the SDK applications output messages to a console window that are of interest from the 
      standpoint of understanding basic OpenCL program flow, and several of the applications generate
      graphics output in a separate OpenGL window.  
      
    - Many of the SDK applications present some timing information useful for obtaining an 
      overall perspective of program structure and flow and the time required for setup and execution of 
      significant functions.  The SDK example code, however, has generally been simplified for instructional 
      purposes and is not optimized.  Advanced optimization techniques are beyond the scope of this SDK, and 
      any timing information presented by the samples is not intended for such usage as benchmarking.  

    - All of the applications additionally log all the console information to a session log file in the
      same directory as the executables.  Those files are named clearly after the name of the sample app, 
      but with a .txt extension.

    - For convenience, the Makefile in <NV_COMPUTE_SDK_PATH>/OpenCL can be used to execute all 
      SDK samples sequentially by typing "make runall" or "make dbg=1 runall".

--------------------------------------------------------------------------------
III.A.  Creating a new OpenCL Program in Windows using the SDK infrastructure 
--------------------------------------------------------------------------------

Creating a new OpenCL Program using the NVIDIA OpenCL SDK infrastructure is easy.
Just follow these steps:

1. Copy one of the installed OpenCL SDK project folders, in its entirety, into 
   "\NVIDIA GPU Computing SDK 4.2\OpenCL\src" and then rename the folder. Now you have 
   a folder such as "\NVIDIA GPU Computing SDK 4.2\OpenCL\src\<myproject>"

2. Edit the filenames of the project to suit your needs.

3. Edit the *.sln, *.vcproj and source files. Just search and replace all
   occurrences of the old filenames to the new ones you chose.

4. Build the 32-bit and/or 64-bit, release and debug configurations using:
      <myproject>_vs2005.sln
	  <myproject>_vs2008.sln
	  <myproject>_vs2010.sln

5. Run <myproject>.exe from the release or debug, directories located in
   "NVIDIA GPU Computing SDK 4.2\OpenCL\bin\win[32|64]\[release|debug]".

6. Modify the code to perform the computation you require. See the OpenCL
   Programming Guide, the OpenCL API Specifications, and the OpenCL Best Practices Guide
   for details of programming in OpenCL.

--------------------------------------------------------------------------------
III.B. Creating Your Own OpenCL Program for Linux using the SDK infrastructure 
--------------------------------------------------------------------------------

Creating a new OpenCL Program using the NVIDIA OpenCL SDK infrastructure is easy.
Just follow these steps:

1. Copy one of the installed OpenCL SDK project folders, in its entirety, into 
   "<NV_COMPUTE_SDK_PATH>/OpenCL/src" and then rename the folder. Now you have 
   a folder such as "<NV_COMPUTE_SDK_PATH>/OpenCL/src/myproject"

2. Edit the filenames of the project to suit your needs.

3. Edit the Makefile. Just search and replace all
   occurrences of the old filenames to the new ones you chose.

4. Build the 32-bit and/or 64-bit, release and debug
   configurations by typing "make" or "make dbg=1".

5. Run your myproject executable from the release or debug, directories located in
   "<NV_COMPUTE_SDK_PATH>/OpenCL/bin/linux/[release|debug]".

6. Modify the code to perform the computation you require. See the OpenCL
   Programming Guide and the OpenCL API Specifications for details of programming in OpenCL.

--------------------------------------------------------------------------------
IV.A. Creating a new OpenCL Program in Windows outside of the SDK infrastructure
--------------------------------------------------------------------------------

To create a new OpenCL Program without using the NVIDIA OpenCL SDK infrastructure, a few 
key files are important to find and utilize.

1. The only OpenCL-specific files needed to build an application to run with NVIDIA
   compute-capable GPU's with CUDA architecture on a system with a supported OS using
   recommended NVIDIA Display drivers supporting OpenCL, are:

   - Headers:
        cl.h
        cl_platform.h        
        cl_ext.h
        cl_gl.h
        cl_gl_ext.h
        cl_d3d11_ext.h
        cl_d3d10_ext.h
        cl_d3d9_ext.h
        opencl.h
        
        These files are located in "NVIDIA GPU Computing SDK 4.2\OpenCL\common\inc\CL"

   - Stub Lib
        OpenCL.lib (different file for Win32 and x64 platforms)

        This .lib files are for build-time implicit linking to the OpenCL driver/compiler, 
        OpenCL.dll, and they are located in: 
        
        "NVIDIA GPU Computing SDK 4.2\OpenCL\common\lib\[Win32|x64] 
            
        Note: These lib files are not needed for applications implementing explicit DLL linkage at run-time.

--------------------------------------------------------------------------------
IV.B.  Creating Your Own OpenCL Program for Linux outside of the SDK infrastructure
--------------------------------------------------------------------------------

To create a new OpenCL Program without using the NVIDIA OpenCL SDK infrastructure, a few
key files are important to find and utilize.

1. The OpenCL-specific files needed to build an application to run with NVIDIA
   compute-capable GPU's with CUDA architecture on a system with a supported OS using
   recommended NVIDIA Display drivers supporting OpenCL, are:

   - Headers:    
        cl.h
        cl_platform.h        
        cl_ext.h
        cl_gl.h
        cl_gl_ext.h
        opencl.h

        These files are located in "NVIDIA GPU Computing SDK 4.2\OpenCL\common\inc\CL"
    
--------------------------------------------------------------------------------
V. (a) Known Issues on Mac OSX
--------------------------------------------------------------------------------
1. On Mac OSX SnowLeopard (10.6) the following 3 SDK samples are not included with the OpenCL SDK package.
   These samples are not currently working on OSX SnowLeopard.  We are working to resolve these issues.
 
   -  oclFDTD3D
   -  oclQuasirandomGenerator   
   -  oclSimpleConvolution 
      
2. As of the release date for this updated SDK (OpenCL 1.0 Release), a mismatch with the OpenCL support 
   on Mac OSX may cause build or execution failures.  The SDK and OpenCL binaries supplied with the 
   258.19 drivers are using the very latest headers from Khronos published June 10, 2010, along with 
   updated NVIDIA extension headers.  But symbols for OpenCL support on Mac OSX are provided in
   OpenCL.framework, and the header files for the revision of OpenCL currently supported on Mac OSX are 
   distributed by Apple, Inc. Information about Mac OSX support for OpenCL is available he:
         
http://developer.apple.com/mac/library/documentation/Performance/Conceptual/OpenCL_MacProgGuide/Introduction/Introduction.html

--------------------------------------------------------------------------------
V. (b) Known Issues on Linux
--------------------------------------------------------------------------------

	1. The SDK samples that make use of OpenGL fail to build or link.  This is because many of the default
       installations for many Linux distributions do not include the necessary OpenGL, GLUT, GLU, GLEW, 
	   X11, Xi, Xlib, or Xmi headers or libraries.  Here are some general and specific solutions:

       (a) Redhat 4 Linux Distributions
	       "ld: cannot find -lglut".  On some linux installations, building the oclSimpleGL example 
		   show the following linking error like the following.

			/usr/bin/ld: cannot find -lglut

	        Typically this is because the SDK makefiles look for libglut.so and not for
	        variants of it (like libglut.so.3). To confirm this is the problem, simply 
	        run the following command.

			ls /usr/lib | grep glut

			ls /usr/lib64 | grep glut

	        You should see the following (or similar) output.

		    lrwxrwxrwx  1 root root     16 Jan  9 14:06 libglut.so.3 -> libglut.so.3.8.0
		    -rwxr-xr-x  1 root root 164584 Aug 14  2004 libglut.so.3.8.0

	        If you have libglut.so.3 in /usr/lib and/or /usr/lib64, simply run the following command 
	        as root.

			ln -s /usr/lib/libglut.so.3 /usr/lib/libglut.so
			ln -s /usr/lib64/libglut.so.3 /usr/lib64/libglut.so

	        If you do NOT have libglut.so.3 then you can check whether the glut package
	        is installed on your RHEL system with the following command.

			rpm -qa | grep glut

	        You should see "freeglut-2.2.2-14" or similar in the output.  If not, you 
	        or your system administrator should install the package "freeglut-2.2.2-14".
	        Refer to the Red Hat and/or rpm documentation for instructions.

	        If you have libglut.so.3 but you do not have write access to /usr/lib, you 
	        can also fix the problem by creating the soft link in a directory to which 
	        you have write permissions and then add that directory to the library 
	        search path (-L) in the Makefile.
        
		(b) Some Linux distributions (i.e. Redhat or Fedora) do not include the GLU library.  
		    You can find the latest packages download this file from this website.  Please 
			make sure you match the correct Linux distribution.

	         http://fr.rpmfind.net/linux/rpm2html/search.php?query=libGLU.so.1&submit=Search+...

        (c) (SLED11) SUSE Linux Enterprise Edition 11 is missing:
	        "libGLU", "libX11" "libXi", "libXm" 

	        This particular version of SUSE Linux 11 does not have the proper symbolic links for the following libraries:

	        i.   libGLU
			
			     ls /usr/lib | grep GLU
		         ls /usr/lib64 | grep GLU

		         libGLU.so.1
		         libGLU.so.1.3.0370300

		         To create the proper symbolic links (32-bit and 64-bit OS)
		       
			     ln -s /usr/lib/libGLU.so.1 /usr/lib/libGLU.so  
		         ln -s /usr/lib64/libGLU.so.1 /usr/lib64/libGLU.so  

	        ii.  libX11
			
		         ls /usr/lib | grep X11
		         ls /usr/lib64 | grep X11
 
		         libX11.so.6
		         libX11.so.6.2.0

		         To create the proper symbolic links  (32-bit and 64-bit OS)
		        
				 ln -s /usr/lib/libX11.so.6 /usr/lib/libX11.so 
		         ln -s /usr/lib64/libX11.so.6 /usr/lib64/libX11.so 

	        iii. libXi
			
		         ls /usr/lib | grep Xi
		         ls /usr/lib64 | grep Xi

		         libXi.so.6
		         libXi.so.6.0.0

		         To create the proper symbolic links (32-bit and 64-bit OS)

		         ln -s /usr/lib/libXi.so.6  /usr/lib/libXi.so 
		         ln -s /usr/lib64/libXi.so.6  /usr/lib64/libXi.so 

	        iv.  libXm
			
		         ls /usr/lib | grep Xm
		         ls /usr/lib64 | grep Xm

		         libXm.so.6
		         libXm.so.6.0.0

		         To create the proper symbolic links (32-bit and 64-bit OS)

		         ln -s /usr/lib/libXm.so.6  /usr/lib/libXm.so 
		         ln -s /usr/lib64/libXm.so.6  /usr/lib64/libXm.so 


	    (d) Ubuntu Linux unable to build these SDK samples that use OpenGL

	        The default Ubuntu distribution is missing many libraries
	   
	        i.  What is missing are the GLUT, Xi, Xmu, GL, and X11 headers.  To add these headers and 
			    libraries to your distribution, type the following in at the command line.
 
	            sudo apt-get install freeglut3-dev build-essential libx11-dev libxmu-dev libxi-dev libgl1-mesa-glx libglu1-mesa libglu1-mesa-dev 
	   
            ii. Note, by installing Mesa, you may see linking errors against libGL.  This can be solved below:
	   
            cd /usr/lib/
            sudo rm libGL.so 
            sudo ln -s libGL.so.1 libGL.so

			
--------------------------------------------------------------------------------
VI. Frequently Asked Questions
--------------------------------------------------------------------------------

Developers participating in an NDA or other early access programs should send
questions, comments, etc. to opencl@nvidia.com and must not discuss their 
experience with 3rd parties.

The official public OpenCL FAQ is available online on the NVIDIA OpenCL Forums:

    http://forums.nvidia.com/index.php?showforum=134

--------------------------------------------------------------------------------
VII.  Change Log (most recent changes listed first)
--------------------------------------------------------------------------------
OpenCL R295 and R300 updated
* Driver support for Kepler GPU architectures.

OpenCL R285 RC1 Update
* Added oclMultiThreads - OpenCL SDK sample that demonstrates how to use the new events and callback functions.
  Note, that by default the oclRelease_vs2005.sln does not include the solution file for oclMultiThreads.
  In order to build this sampke with VS2005, you must install the Microsoft SDK v6.0 or newer.  VS2008 and VS2010
  projects are included with this sample.

OpenCL R280 Update
* Adds support for OpenCL 1.1

OpenCL R270 Update
* Added VS2010 project support for OpenCL SDK samples, SDK samples will now build with Visual Studio 2010
* Added SDK sample: oclInlinePTX - demonstrates how to embed PTX within OpenCL kernels
* Updated OpenCL individual SDK sample solution files (*.sln) for VS2005, VS2008, and VS2010.  
  Now the individual solutions include project dependencies with SDK helper libraries.  If a SDK sample
  depend on linking with shrUtils or oclUtils, the individual OpenCL SDK samples can now be built 
  without using oclRelease_vs20??.sln to build its dependencies.

OpenCL R260 Release
* Added SDK sample: oclMarchingCubes

OpenCL R260 Beta Release Candidate
* Added SDK sample: oclTridiagonal

OpenCL 1.0 Release
* Added SDK samples: oclSimpleD3D9Texture, oclSimpleD3D10Texture
* Removed work-around in oclCopyComputeOverlap due to fixes in 258.19 driver
* Miscellaneous cleanups, bug fixes and improvements

OpenCL R256 Beta
* Added SDK samples: oclHiddenMarkovModel, oclSimpleD3D9Texture, and oclSimpleD3D10Texture
* Minor cleanups and improvements

OpenCL R195 Release
* All OpenCL headers from Khronos updated
* NVIDIA OpenCL extension headers updated and 4 new ones added
	(cl_gl_ext.h, cl_d3d11_ext.h, cl_d3d10_ext.h, cl_d3d9_ext.h)
* Support for ICD, CL-GL interop and CL-D3D interop
	http://www.khronos.org/registry/cl/
* Some SDK samples using both OpenGL and OpenCL have been updated to use new CL-GL interop
* Added oclCopyComputeOverlap
  - Demonstrates how to handle copy and kernel execution with OpenCL
* Bug fixes and improvements
* Updated documentation

OpenCL R195 Update Release
* Miscellaneous SDK source code refinements in conjunction with updated/improved drivers
* Included Khronos OpenCL Specification and quick reference card updated to latest versions
* clext.h file name changed to cl_ext.h
* Enumeration names for extensions in cl_ext.h have been updated
* OpenCL.lib updated for change in OpenCL.dll (distributed separately with driver) from __cdecl to __stdcall   
* Previous NVIDIA OpenCL drivers permitted developers to assume that the NULL or default platform, 
  as passed to clCreateContext and related calls, was NVIDIA's platform. This approach is incompatible 
  with supporting multiple vendors on a single platform (it would be unclear which vendor is the default). 
  To prepare for compatibility with future multi-vendor OpenCL installations, NVIDIA’s drivers will no longer 
  honor NULL as a platform. This requires OpenCL programs to be changed explicitly enumerate the 
  available platforms and choose the appropriate vendors.  This change is reflected in the sample code
  in this SDK release.

OpenCL R190 Update Release
* OpenCL compiler/driver moved from SDK to r190 GPU driver
* OpenCL compiler/driver includes a number of fixes, extensions and performance improvements 
* Updated OpenCL headers and libs 
* Required/supplied r190 driver is compatible with CUDA 2.3
* Added: Support for Windows 7 (32 bit and 64 bit)
* Unified 32 bit Windows SDK packages for Win32 target. (32 bit Windows XP, Vista, Win7) = 1 SDK installer package
* Unified 64 bit Windows SDK packages for x64 target. (64 bit Windows XP, Vista, Win7) = 1 SDK installer package
* Cross compilation (32/64 and 64/32) now works for OpenCL sample projects
* SDK Version 4788711 
  Numerous revisions to SDK sample code, including multi-GPU support on several samples
  Added samples:  oclMedianFilter, oclFDTD3d, oclRadixSort, 
                  oclMersenneTwister, oclSemirandomGenerator,
                  oclMatVecMul, oclHiddenMarkovModel
* SDK samples now support Mac OSX SnowLeopard, but a few are excluded.  See Known Issues.
* Added OpenCL Best Practices Guide
* Added OpenCL Programming Overview
* One set of unified Release Notes for Windows and Linux
* Updated other documentation

OpenCL 1.0 Conformant Release
* Minor revisions to SDK content & added oclSobelFilter sample, SDK 1.00.00.07
* OpenCL conformance 

OpenCL 1.0 Beta 1.2
* Minor revisions to SDK content, SDK 1.00.00.06
* Bundle new OpenCL spec (v 1.00.43) from Khronos

OpenCL 1.0 Beta 1.1
* Vista32 and Vista64 OpenCL pre-release binaries revised to equivalent version as other platforms
* Minor revisions to SDK content reflecting updated Vista 32 and 64 OpenCL binaries, SDK 1.00.00.05

OpenCL 1.0 Beta 1
* WinXP 32, WinXP64, Linux 32 & 64 (Kernel Version 2.6), WinVista 32 and WinVista 64 supported  
* Updated GPU Display drivers to public WHQL driver 185.85 (Win) & 185.18.08 (Linux)
  (GPU drivers are now compatible with CUDA 2.2 and OpenCL)
* Elimination of most previous known issues for WinXP 32 & 64 and Linux 32 & 64
* Misc. other updates and improvements, SDK 1.00.00.04

OpenCL 1.0 Conformance Candidate Release 
* WinXP 32 and Linux 32 (Kernel Version 2.6) supported  
* Updated GPU Display drivers to public WHQL driver 185.85 (Win) & 185.18.08 (Linux)
  (GPU drivers are now compatible with CUDA 2.2 and OpenCL)
* Elimination of most previous known issues for WinXP 32 and Linux 32 
* Misc. other updates and improvements

Release 1.0 Alpha 2.1 
* Add support for 64 bit WinXP, WinVista and Linux (Ubuntu 8.1).  
* Misc. updates and improvements

Release 1.0 Alpha 2 Windows Driver Refresh
* Update for new Windows GPU drivers plus other corrections, additions, clarifications

Release 1.0 Alpha 2
* First Developer-Partner NDA Release

--------------------------------------------------------------------------------
VIII. OS Platforms and Compilers Supported
--------------------------------------------------------------------------------

[Windows Platforms]
	OS Platform Support with CUDA 4.2
		* Support for Kepler based GPUs

	OS Platform Support with CUDA 4.1
		* No changes
	
	OS Platform Support with CUDA 4.0
		* New Compilers supported
			o Visual Studio 10 (2010) 
		* Continued supported compilers
			o Visual Studio 9  (2008) 
			o Visual Studio 8  (2005) 
		* Continued supported OS
			Windows XP, Windows Vista, Windows 7
			Windows Server 2008 and 2008 R2

	OS Platform Support added to CUDA 3.0 Release
		* Windows 7 32 & 64
		* Windows Server 2008 & 2008 R2
		
	OS Platform Support added to CUDA 2.2
		* Vista 32 & 64bit, WinXP 32 & 64-bit
			  o Visual Studio 9 (2008) 
			  o Visual Studio 8 (2005)

[Mac Platforms]
	OS Platform Support with CUDA 4.2
		* Support for Kepler based GPUs
		
	OS Platform Support with CUDA 4.1
	    * No changes

	OS Platform Support with CUDA 4.0
		* New OS Platforms added
			MacOS X Lion 10.7.x
		* Continued OS Platforms
			MacOS X SnowLeopard 10.6.x

	OS Platform Support added to CUDA 3.2 
		* MacOS X SnowLeopard 10.6.5
		* MacOS X SnowLeopard 10.6.4

	OS Platform Support added to CUDA 3.1 Beta
		* MacOS X SnowLeopard 10.6.3

	OS Platform Support added to CUDA 3.0 Release
		* MacOS X SnowLeopard 10.6.x
				  
	OS Platform Support added to CUDA 3.0 Beta 1
		* MacOS X SnowLeopard 10.6 (32-bit)
			  

[Linux Platforms]
	OS Platform Support with CUDA 4.2
		* Support for Kepler based GPUs

	OS Platform Support with CUDA 4.1
		* New OS Platforms added
			   Ubuntu 11.04,
			   Fedora 14,
			   RHEL-5.5, 5.6, 5.7 (32-bit and 64-bit)
			   RHEL-6.X (6.0, 6.1) (64-bit only),
			   ICC Compiler 11.1 (32-bit and 64-bit linux)
		* Continued OS Platforms
			   SLES 11.1,
			   Ubuntu 10.04,
			   OpenSUSE-11.2
		* Platforms no longer supported 
			   Ubuntu 10.10,
			   Fedora 13,
			   RHEL-4.8

	OS Platform Support with CUDA 4.0
		* New OS Platforms added
			   SLES11-SP1,
			   RHEL-6.0 (64-bit only),
			   Ubuntu 10.10
		* Continued OS Platforms
			   OpenSUSE-11.2
			   Fedora 13,
			   RHEL-4.8 (64-bit only),
			   RHEL-5.5
		* Platforms no longer supported 
			   RHEL-4.8 (32-bit only)
			   Ubuntu 10.04,
			   SLED11-SP1
					   
	OS Platform Support added to CUDA 3.2
		* Additional Platform Support Linux 32 & 64: 
			   Fedora 13,
			   Ubuntu 10.04,
			   RHEL-5.5,
			   SLED-11SP1,
			   ICC (64-bit linux only?)
		* Platforms no longer supported
			   Fedora 12,
			   Ubuntu 9.10
			   RHEL-5.4,
			   SLED11

	OS Platform Support added to CUDA 3.1
		* Additional Platform Support Linux 32 & 64: 
			   Fedora 12,
			   OpenSUSE-11.2,
			   Ubuntu 9.10
			   RHEL-5.4
		* Platforms no longer supported 
			   Fedora 10,
			   OpenSUSE-11.1,
			   Ubuntu 9.04

	OS Platform Support added to CUDA 3.0
		* Linux Distributions 32 & 64: 
				RHEL-4.x (4.8),
				RHEL-5.x (5.3), 
				SLED-11
				Fedora10,         
				Ubuntu 9.04,
				OpenSUSE 11.1
				  o gcc 3.4, gcc 4 

