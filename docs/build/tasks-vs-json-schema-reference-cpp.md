---
title: Tasks. vs. JSON şema başvurusu (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 1e533babafad554e8f7413d2bc1a88933a6eca42
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975919"
---
# <a name="tasksvsjson-schema-reference-c"></a>Tasks. vs. JSON şema başvurusu (C++)

Visual Studio 'Yu açık bir klasör projesinde kaynak kodunuzu nasıl derleyeceğinizi söylemek için bir *Tasks. vs. JSON* dosyası ekleyin. Burada herhangi bir rastgele görevi tanımlayabilir ve ardından **Çözüm Gezgini** bağlam menüsünden çağırabilirsiniz. CMake projeleri, *Cmakelists. txt*dosyasında tüm derleme komutları belirtildiğinden bu dosyayı kullanmaz. CMake dışındaki derleme sistemlerinde, *Tasks. vs. JSON* , derleme komutlarını belirtebileceğiniz ve derleme betikleri çağırabileceğiniz yerdir. *Tasks. vs. JSON*kullanma hakkında genel bilgi için bkz. ["klasör açma" geliştirmesi için derleme ve hata ayıklama görevlerini özelleştirme](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio).

Bir görev, dört `type` değerden birine sahip olabilecek bir özelliğe sahiptir: `default`, `launch`, `remote`veya `msbuild`. Birçok görev, uzak `launch` bir bağlantı gerekmiyorsa kullanılmalıdır.

## <a name="default-properties"></a>Varsayılan Özellikler

Tüm görev türlerinde varsayılan özellikler mevcuttur:

||||
|-|-|-|
|**Özelliði**|**Tür**|**Açıklama**|
|`taskLabel`|dize| (Gerekli.) Kullanıcı arabiriminde kullanılan görev etiketini belirtir.|
|`appliesTo`|dize| (Gerekli.) Komutun hangi dosyalara uygulanabilir olduğunu belirtir. Joker karakter kullanımı desteklenir, örneğin: " *", "* . cpp", "/*. txt"|
|`contextType`|dize| İzin verilen değerler: "özel", "derleme", "Temizle", "yeniden derle". Görevin bağlam menüsünde nerede görüneceğini belirler. Varsayılan "Custom" olarak belirlenmiştir.|
|`output`|dize| Göreviniz için bir çıkış etiketi belirtir.|
|`inheritEnvironments`|dizi| Birden çok kaynaktan devralınan bir ortam değişkenleri kümesini belirtir. *Cmakesettings. JSON* veya *cppproperties. JSON* gibi dosyalardaki değişkenleri tanımlayabilir ve bunları görev bağlamı için kullanılabilir hale getirebilirsiniz.|
|`passEnvVars`|Boole değeri| Görev bağlamına ek ortam değişkenlerinin eklenip eklenmeyeceğini belirtir. Bu değişkenler, `envVars` özelliği kullanılarak tanımlandıklarından farklıdır. Varsayılan değer "true" olarak belirlenmiştir.|

## <a name="launch-properties"></a>Başlatma özellikleri

Görev türü `launch`olduğunda, bu özellikler kullanılabilir:

||||
|-|-|-|
|**Özelliði**|**Tür**|**Açıklama**|
|`command`|dize| Başlatılacak işlemin veya betiğin tam yolunu belirtir.|
|`args`|dizi| Komuta geçirilen bağımsız değişkenlerin virgülle ayrılmış bir listesini belirtir.|
|`launchOption`|dize| İzin verilen değerler: "None", "devam eden", "IgnoreError". Hatalar olduğunda komutla nasıl devam etmek istediğinizi belirtir.|
|`workingDirectory`|dize| Komutun çalıştırılacağı dizini belirtir. Projenin geçerli çalışma dizinini varsayılan olarak belirler.|
|`customLaunchCommand`|dize| Komutu yürütmeden önce uygulanacak genel kapsam özelleştirmesini belirtir. % PATH% gibi ortam değişkenlerini ayarlamak için faydalıdır.|
|`customLaunchCommandArgs`|dize| CustomLaunchCommand için bağımsız değişkenleri belirtir. (Gerektirir `customLaunchCommand`.)|
 `env`| Özel ortam değişkenlerinin anahtar-değer listesini belirtir. Örneğin, "myEnv": "myVal"|
|`commands`|dizi| Sırayla çağrılacak komutların listesini belirtir.|

### <a name="example"></a>Örnek

Aşağıdaki görevler, klasöründe bir derleme görevleri dosyası sağlandığında ve `Mingw64` bu ortam cppproperties. JSON içinde tanımlanmışsa, [cppproperties. JSON Şema başvurusunda](cppproperties-schema-reference.md#user_defined_environments)gösterildiği gibi *Make. exe* ' yi çağırır:

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

Uzak görevler, Linux geliştirmesini C++ iş yüküne yüklediğinizde ve Visual Studio bağlantı Yöneticisi 'ni kullanarak uzak makineye bir bağlantı eklediğinizde etkinleştirilir. Uzak bir görev, uzak bir sistemde komutlar çalıştırır ve ayrıca dosyaları buna kopyalayabilir.

Görev türü `remote`olduğunda, bu özellikler kullanılabilir:

||||
|-|-|-|
|**Özelliði**|**Tür**|**Açıklama**|
|`remoteMachineName`|dize|Uzak makinenin adı. **Bağlantı yöneticisinde**bir makine adıyla eşleşmelidir.|
|`command`|dize|Uzak makineye gönderme komutu. Varsayılan olarak komutlar, uzak sistemdeki $HOME dizininde yürütülür.|
|`remoteWorkingDirectory`|dize|Uzak makinedeki geçerli çalışma dizini.|
|`localCopyDirectory`|dize|Uzak makineye kopyalanacak yerel dizin. Geçerli çalışma dizinini varsayılan olarak belirler.|
|`remoteCopyDirectory`|dize|İçine kopyalanmış olan `localCopyDirectory` uzak makinedeki dizin.|
|`remoteCopyMethod`|dize| Kopyalama için kullanılacak yöntem. İzin verilen değerler: "none", "SFTP", "rsync". büyük projeler için rsync önerilir.|
|`remoteCopySourcesOutputVerbosity`|dize| İzin verilen değerler: "Normal", "ayrıntılı", "Tanılama".|
|`rsyncCommandArgs`|dize|Varsayılan olarak "-t--Delete" olarak belirlenmiştir.|
|`remoteCopyExclusionList`|dizi|Kopyalama işlemlerinden hariç tutulacak dosyaların `localCopyDirectory` virgülle ayrılmış listesi.|

### <a name="example"></a>Örnek

**Çözüm Gezgini**'de *Main. cpp* öğesine sağ tıkladığınızda, bağlam menüsünde aşağıdaki görev görüntülenir. `ubuntu` **Bağlantı Yöneticisi**'nde çağrılan uzak makineye bağlıdır. Görev, Visual Studio `sample` 'daki geçerli açık klasörü uzak makinedeki dizine kopyalar ve ardından programı derlemek için g + + çağırır.

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

Görev türü `msbuild`olduğunda, bu özellikler kullanılabilir:

||||
|-|-|-|
|**Özelliði**|**Tür**|**Açıklama**|
|`verbosity`|dize| MSBuild proje derlemesi çıkış verbosityAllowed değerlerini belirtir: "Sessiz", "minimal", "normal", "ayrıntılı", "Tanılama".|
|`toolsVersion`|dize| Projeyi derlemek için araç takımı sürümünü belirtir, örneğin "2,0", "3,5", "4,0", "Current". Varsayılan olarak "geçerli" olur.|
|`globalProperties`|nesne|Projeye geçirilecek genel özelliklerin anahtar-değer listesini belirtir, örneğin, "yapılandırma": "yayın"|
|`properties`|nesne| Yalnızca ek proje özelliklerinin anahtar-değer listesini belirtir.|
|`targets`|dizi| Üzerinde çağrılacak hedeflerin listesini proje üzerinde belirtir. Hiçbiri belirtilmemişse projenin varsayılan hedefi kullanılır.|
