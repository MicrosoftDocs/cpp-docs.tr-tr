---
title: Şema başvurusunda tasks.vs.js(C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: a2aea1b64d5a6c62604c680bf1a4a26478b7b52a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844996"
---
# <a name="tasksvsjson-schema-reference-c"></a>Şema başvurusunda tasks.vs.js(C++)

Visual Studio 'Yu açık bir klasör projesinde kaynak kodunuzu nasıl derleyeceğinizi söylemek için dosyasına bir *tasks.vs.js* ekleyin. Burada herhangi bir rastgele görevi tanımlayabilir ve ardından **Çözüm Gezgini** bağlam menüsünden çağırabilirsiniz. Tüm derleme komutları *CMakeLists.txt*belirtildiğinden CMake projeleri bu dosyayı kullanmaz. CMake dışındaki derleme sistemlerinde, derleme komutlarını belirtebileceğiniz ve derleme betikleri çağırabileceğiniz *tasks.vs.js* . *Üzerindetasks.vs.js*kullanma hakkında genel bilgi için, bkz. ["klasör açma" geliştirmesi için derleme ve hata ayıklama görevlerini özelleştirme](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio).

Bir görev, `type` dört değerden birine sahip olabilecek bir özelliğe sahiptir: `default` , `launch` , `remote` veya `msbuild` . Birçok görev `launch` , uzak bir bağlantı gerekmiyorsa kullanılmalıdır.

## <a name="default-properties"></a>Varsayılan Özellikler

Tüm görev türlerinde varsayılan özellikler mevcuttur:

|Özellik|Tür|Description|
|-|-|-|
|`taskLabel`|dize| (Gerekli.) Kullanıcı arabiriminde kullanılan görev etiketini belirtir.|
|`appliesTo`|string| (Gerekli.) Komutun hangi dosyalara uygulanabilir olduğunu belirtir. Joker karakter kullanımı desteklenir, örneğin: "*", "*. cpp", "/*. txt"|
|`contextType`|string| İzin verilen değerler: "özel", "derleme", "Temizle", "yeniden derle". Görevin bağlam menüsünde nerede görüneceğini belirler. Varsayılan "Custom" olarak belirlenmiştir.|
|`output`|string| Göreviniz için bir çıkış etiketi belirtir.|
|`inheritEnvironments`|array| Birden çok kaynaktan devralınan bir ortam değişkenleri kümesini belirtir. *CMakeSettings.js* veya *CppProperties.js* gibi dosyalardaki değişkenleri tanımlayabilir ve bunları görev bağlamı için kullanılabilir hale getirebilirsiniz. **Visual Studio 16,4:**: sözdizimini kullanarak görev başına temelinde ortam değişkenlerini belirtin `env.VARIABLE_NAME` . Bir değişkeni kaldırmak için, "null" olarak ayarlayın.|
|`passEnvVars`|boolean| Görev bağlamına ek ortam değişkenlerinin eklenip eklenmeyeceğini belirtir. Bu değişkenler, özelliği kullanılarak tanımlandıklarından farklıdır `envVars` . Varsayılan değer "true" olarak belirlenmiştir.|

## <a name="launch-properties"></a>Başlatma özellikleri

Görev türü olduğunda `launch` , bu özellikler kullanılabilir:

|Özellik|Tür|Description|
|-|-|-|
|`command`|dize| Başlatılacak işlemin veya betiğin tam yolunu belirtir.|
|`args`|array| Komuta geçirilen bağımsız değişkenlerin virgülle ayrılmış bir listesini belirtir.|
|`launchOption`|string| İzin verilen değerler: "none", "devam eden", "IgnoreError". Hatalar olduğunda komutla nasıl devam etmek istediğinizi belirtir.|
|`workingDirectory`|string| Komutun çalıştırılacağı dizini belirtir. Projenin geçerli çalışma dizinini varsayılan olarak belirler.|
|`customLaunchCommand`|string| Komutu yürütmeden önce uygulanacak genel kapsam özelleştirmesini belirtir. % PATH% gibi ortam değişkenlerini ayarlamak için faydalıdır.|
|`customLaunchCommandArgs`|string| CustomLaunchCommand için bağımsız değişkenleri belirtir. (Gerektirir `customLaunchCommand` .)|
 `env`| Özel ortam değişkenlerinin anahtar-değer listesini belirtir. Örneğin, "myEnv": "myVal"|
|`commands`|array| Sırayla çağrılacak komutların listesini belirtir.|

### <a name="example"></a>Örnek

Aşağıdaki görevler, veritabanında *make.exe* bir derleme görevleri dosyası sağlandığında ve `Mingw64` ortam *CppProperties.js*' de tanımlandığı gibi, [şema başvurusundaCppProperties.js](cppproperties-schema-reference.md#user_defined_environments)gösterildiği gibimake.exeçağırır:

```json
 {
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "gcc make",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make"
    },
    {
      "taskLabel": "gcc clean",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make",
      "args": ["clean"]
    }
  ]
}
```

Bu görevler, **Çözüm Gezgini**bir *. cpp* dosyasına sağ tıkladığınızda bağlam menüsünden çağrılabilir.

## <a name="remote-properties"></a>Uzak Özellikler

C++ iş yüküyle Linux geliştirmeyi yüklediğinizde ve Visual Studio bağlantı Yöneticisi 'Ni kullanarak uzak makineye bir bağlantı eklediğinizde uzak görevler etkinleştirilir. Uzak bir görev, uzak bir sistemde komutlar çalıştırır ve ayrıca dosyaları buna kopyalayabilir.

Görev türü olduğunda `remote` , bu özellikler kullanılabilir:

|Özellik|Tür|Description|
|-|-|-|
|`remoteMachineName`|dize|Uzak makinenin adı. **Bağlantı yöneticisinde**bir makine adıyla eşleşmelidir.|
|`command`|string|Uzak makineye gönderme komutu. Varsayılan olarak komutlar, uzak sistemdeki $HOME dizininde yürütülür.|
|`remoteWorkingDirectory`|string|Uzak makinedeki geçerli çalışma dizini.|
|`localCopyDirectory`|string|Uzak makineye kopyalanacak yerel dizin. Geçerli çalışma dizinini varsayılan olarak belirler.|
|`remoteCopyDirectory`|string|İçine kopyalanmış olan uzak makinedeki Dizin `localCopyDirectory` .|
|`remoteCopyMethod`|string| Kopyalama için kullanılacak yöntem. İzin verilen değerler: "none", "SFTP", "rsync". büyük projeler için rsync önerilir.|
|`remoteCopySourcesOutputVerbosity`|string| İzin verilen değerler: "normal", "verbose", "Tanılama".|
|`rsyncCommandArgs`|string|Varsayılan olarak "-t--Delete" olarak belirlenmiştir.|
|`remoteCopyExclusionList`|array|`localCopyDirectory`Kopyalama işlemlerinden hariç tutulacak dosyaların virgülle ayrılmış listesi.|

### <a name="example"></a>Örnek

**Çözüm Gezgini**'de *Main. cpp* öğesine sağ tıkladığınızda, bağlam menüsünde aşağıdaki görev görüntülenir. `ubuntu` **Bağlantı Yöneticisi**'nde çağrılan uzak makineye bağlıdır. Görev, Visual Studio 'daki geçerli açık klasörü `sample` uzak makinedeki dizine kopyalar ve ardından programı derlemek için g + + çağırır.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Build",
      "appliesTo": "main.cpp",
      "type": "remote",
      "contextType": "build",
      "command": "g++ main.cpp",
      "remoteMachineName": "ubuntu",
      "remoteCopyDirectory": "~/sample",
      "remoteCopyMethod": "sftp",
      "remoteWorkingDirectory": "~/sample/hello",
      "remoteCopySourcesOutputVerbosity": "Verbose"
    }
  ]
}
```

## <a name="msbuild-properties"></a>MSBuild özellikleri

Görev türü olduğunda `msbuild` , bu özellikler kullanılabilir:

|Özellik|Tür|Description|
|-|-|-|
|`verbosity`|dize| MSBuild proje derlemesi çıkış verbosityAllowed değerlerini belirtir: "sessiz", "minimal", "normal", "ayrıntılı", "Tanılama".|
|`toolsVersion`|string| Projeyi derlemek için araç takımı sürümünü belirtir, örneğin "2,0", "3,5", "4,0", "Current". Varsayılan olarak "geçerli" olur.|
|`globalProperties`|object|Projeye geçirilecek genel özelliklerin anahtar-değer listesini belirtir, örneğin, "yapılandırma": "yayın"|
|`properties`|object| Yalnızca ek proje özelliklerinin anahtar-değer listesini belirtir.|
|`targets`|array| Üzerinde çağrılacak hedeflerin listesini proje üzerinde belirtir. Hiçbiri belirtilmemişse projenin varsayılan hedefi kullanılır.|
