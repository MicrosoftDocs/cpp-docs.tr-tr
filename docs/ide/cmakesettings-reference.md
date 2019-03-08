---
title: CMakeSettings.json şema başvurusu
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: d80829b1475e8718e1c4188ff4fb7d42a1d4b3b9
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566922"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json şema başvurusu

`cmakesettings.json` Dosya Visual Studio'nun belirli bir platform için bir proje oluşturmak için CMake ile nasıl etkileşim kuracağını belirten bilgileri içerir. Ortam değişkenleri ya da cmake.exe ortam için bağımsız değişkenler gibi bilgileri depolamak için bu dosyayı kullanın.

## <a name="environments"></a>Ortamlar

`environments` Dizi listesini içeren `items` türü `object` , tanımladığınız bir "ortam." Bir ortam değişkenleri kümesi uygulamak için kullanılabilir bir `configuration`. Her öğe `environments` dizi oluşur:

- `namespace`: ortam değişkenlerini biçiminde bir yapılandırma başvurulabilir, böylece adları `namespace.variable`. Varsayılan ortam nesne adında `env` ve sistem ortam değişkenlerini de dahil olmak üzere belirli doldurulur `%USERPROFILE%`.
- `environment`: Bu değişken grubu benzersiz olarak tanımlar. Grubun daha sonra devralınmasını sağlar bir `inheritEnvironments` girişi.
- `groupPriority`: Önceliği bu değişkenlerin değerlendirilme sırasındaki belirten bir tamsayı. İlk olarak daha yüksek sayıya sahip öğeler değerlendirilir.
- `inheritEnvironments`: Bu grup tarafından devralınan ortamlar kümesi belirten değerleri dizisi. Önceden tanımlanmış bu ortamları veya herhangi bir özel ortama kullanılabilir:
 
  - linux_arm: ARM Linux'u uzaktan hedefleyin.
  - linux_x64: Hedef x64 Linux uzaktan.
  - linux_x86: Hedef x86 Linux uzaktan.
  - msvc_arm: MSVC derleyicisi ile ARM Windows hedef.
  - msvc_arm_x64: 64 bit MSVC derleyicisi ile ARM Windows hedef.
  - msvc_arm64: MSVC derleyicisi ile ARM64 Windows hedef.
  - msvc_arm64_x64: 64 bit MSVC derleyicisi ile ARM64 Windows hedef.
  - msvc_x64: MSVC derleyicisi ile hedef x64 Windows.
  - msvc_x64_x64: Hedef x64 Windows 64 bit MSVC derleyicisi ile.
  - msvc_x86: MSVC derleyicisi ile hedef x86 Windows.
  - msvc_x86_x64: Hedef x86 Windows 64 bit MSVC derleyicisi ile.

## <a name="configurations"></a>Yapılandırmalar

`configurations` Aynı klasördeki CMakeLists.txt dosyasına uygulanan CMake yapılandırmaları temsil eden nesneler dizisi oluşur. Bu nesneler, birden çok derleme yapılandırmalarını tanımlamak ve bunları IDE'de arasında kolayca geçiş için kullanabilirsiniz. 

A `configuration` şu özelliklere sahiptir:
- `name`: yapılandırma adları.
- `description`: menülerde görünür bu yapılandırma açıklaması.
- `generator`: Bu yapılandırma için kullanılacak CMake Oluşturucu belirtir. Aşağıdakilerden biri olabilir:

  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 2015 14 ARM
  - UNIX derleme görevleri dosyası
  - Ninja

- `configurationType`: Seçili Oluşturucu için derleme türü yapılandırmasını belirler. Aşağıdakilerden biri olabilir:
 
  - Hata ayıklama
  - Sürüm
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: Bu yapılandırmanın bağımlı olduğu bir veya daha fazla ortam belirtir. Herhangi bir özel ortama veya önceden tanımlanmış ortamlar biri olabilir.
- `buildRoot`: belirtir directory cmake'in derleme komut dosyası için seçilen Oluşturucusu. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`. "
- `installRoot`: cmake'in seçili Oluşturucu için yükleme hedefleri dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`. "
- `cmakeCommandArgs`: önbelleği oluşturması için çağrıldığında Cmake'e geçirilen ek komut satırı seçenekleri belirtir. "
- `cmakeToolchain`: araç zinciri dosyasını belirtir. Bu Cmake'e geçirilen kullanma - DCMAKE_TOOLCHAIN_FILE. "
- `buildCommandArgs`: yerel derleme anahtarları--build--Cmake'e geçirilen belirtir. "
- `ctestCommandArgs`: ek komut satırı seçenekleri, testler çalıştırıldığında Ctest'e geçirilen belirtir. "
- `codeAnalysisRuleset`: Kod Analizi çalıştırırken kullanılacak ruleset belirtir. Bu bir tam yol veya Visual Studio tarafından yüklenmiş bir ruleset dosyasının dosya adı olabilir."
- `intelliSenseMode`: IntelliSense bilgilerinin hesaplanmasında kullanılan mod belirtir ". Aşağıdakilerden biri olabilir:
 
  - windows-msvc-x86
  - windows-msvc-x64
  - Windows msvc arm
  - Windows msvc arm64
  - Android clang x86
  - Android clang x64
  - Android-clang-arm
  - Android clang arm64
  - iOS clang x86
  - iOS clang x64
  - iOS-clang-arm
  - iOS clang arm64
  - Windows clang x86
  - windows-clang-x64
  - Windows-clang-arm
  - windows-clang-arm64
  - Linux gcc x86
  - Linux gcc x64
  - Linux-gcc-arm"

- `cacheRoot`: bir CMake önbelleği yolunu belirtir. Bu dizin mevcut bir CMakeCache.txt dosyasını içermesi gerekir.
- `remoteMachineName`: Cmake'i, derlemeleri ve hata ayıklayıcı barındıran uzak Linux makinesinin adını belirtir. Yeni Linux makineleri eklemek için Bağlantı Yöneticisi'ni kullanın. Desteklenen makrolar `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: işlem uzak makineye kopyalanıyor kaynak ayrıntı düzeyini belirtir. "Yalnızca"Normal","Ayrıntılı"veya"Tanılama". olabilir
- `remoteCopySourcesConcurrentCopies`: kaynakların Uzak makineyle eşitlenmesi sırasında kullanılan eş zamanlı kopyaların sayısını belirtir.
- `remoteCopySourcesMethod`: dosyalar uzak makineye kopyalamak için yöntemini belirtir. "Rsync" veya "sftp" olabilir.
- `remoteCMakeListsRoot`: uzak makinede CMake projesini içeren dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: cmake'in seçili Oluşturucu için derleme betikleri uzak bir makinede dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: uzak makinede cmake'in seçili Oluşturucu için yükleme hedefleri dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, ve `${env.VARIABLE}` burada `VARIABLE` sahip bir ortam değişkeni Sistem, kullanıcı veya oturum düzeyinde tanımlanmış.
- `remoteCopySources`: A `boolean` Visual Studio kaynak dosyaları uzak makineye kopyalayın olup olmadığını belirtir. Varsayılan değer True'dur. Dosya eşitlemesini kendiniz yönetiyorsanız false olarak ayarlayın.
- `remoteCopyBuildOutput`: A `boolean` yapı çıkışlarını Uzak sistemden kopyalanıp kopyalanmayacağını belirtir.
- `rsyncCommandArgs`: rsync metoduna geçirilen ek komut satırı seçeneklerini belirtir.
- `remoteCopySourcesExclusionList`: A `array` kaynak dosyaları kopyalarken hariç tutulacak yolları listesi belirten: bir yolu, dosya/dizin veya kopya köküne göreli bir yol adı olabilir. Joker karakterler \\ \" * \\ \" ve \\ \"?\\ \" glob deseni eşleştirmek için kullanılabilir.
- `cmakeExecutable`: dosya adı ve uzantısıyla birlikte CMake programı yürütülebilir tam yolunu belirtir.
- `remotePreGenerateCommand`: CMakeLists.txt dosyasını ayrıştırmak için Cmake'i çalıştırmadan önce çalıştırılacak komutu belirtir.
- `remotePrebuildCommand`: derlemeden önce uzak makinede çalıştırılacak komutu belirtir.
- `remotePostbuildCommand`: derlemeden sonra uzak makinede çalıştırılacak komutu belirtir.
- `variables`: A `array` cmake'e - Dname1 olarak geçirilen değişkenleri belirten = değer1-Dname2 = değer2 vb. 


