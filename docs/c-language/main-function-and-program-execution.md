---
title: Main işlevi ve Program yürütme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- main function, program execution
- startup code, main function
- main function
- programs [C++], terminating
ms.assetid: 5984f1bd-072d-4e06-8640-122fb1454401
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca08ecc5be82ec256320c87a9a49e354dccd40f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="main-function-and-program-execution"></a>main İşlevi ve Program Yürütme
Her C programı adlandırılmalıdır birincil bir (ana) işlevi olan **ana**. Unicode programlama modeli kodunuzu aynılarını, joker karakter sürümünü kullanabilirsiniz **ana**, **wmain**. **Ana** programın yürütülmesi için başlangıç noktası işlevi görür. Genellikle çağrıları programdaki diğer işlevlere yönlendirerek program yürütmesini denetler. Bir program genellikle sonunda yürütülmesi durdurulur **ana**, çeşitli nedenlerle için programında diğer noktalarda sonlandırabilir rağmen. Bazen belirli bir hata algılandığında, programı sonlandırılmaya zorlamak isteyebilirsiniz. Bunu yapmak için kullanın **çıkmak** işlevi. Bkz: *çalışma zamanı kitaplığı başvurusu* hakkında bilgi ve bir örnek kullanmak için [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
main( int argc, char *argv[ ], char *envp[ ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak programının içerisindeki işlevler, bir veya daha fazla belirli görevi gerçekleştirir. **Ana** işlevi, kendi görevlerini gerçekleştirmek için bu işlevleri çağırabilir. Zaman **ana** başka bir işlevi çağırdığı işlevi ilk deyiminde yürütme başlangıcı böylece işleve yürütme denetimi geçirir. Denetim için bir işlev döndürür **ana** zaman bir `return` deyimi yürütüldüğünde veya işlevin sonuna ulaşıldığında.  
  
 Herhangi bir işlev bildirebilir dahil olmak üzere **ana**, parametreleri sağlamak için. "Parametre" veya "biçimsel parametre" terimi, işleve geçirilen bir değeri alan tanımlayıcı anlamına gelir. Bkz: [parametreleri](../c-language/parameters.md) parametreleri bağımsız değişkenleri geçirme hakkında bilgi için. Bir işlev diğerini çağırdığında, çağrılan işlev çağıran işlevden parametrelerine yönelik değerleri alır. Bu değerlere "bağımsız değişkenler" adı verilir. Biçimsel parametresi bildirebilir **ana** böylece bu biçimi kullanarak komut satırından bağımsız değişkenleri alabilir:  
  
 Bilgileri geçirmek istiyorsanız **ana** işlevi geleneksel olarak adlandırılmış parametreleri `argc` ve `argv`, C derleyicisi bu adları gerekli olmasa da. `argc` ve `argv` türleri, C dili tarafından tanımlanır. Geleneksel olarak, üçüncü parametre iletilir **ana**, bu parametrenin adlı `envp`. Bu bölümdeki diğer örnekler, komut satırı bağımsız değişkenlerine erişmek için bu üç parametrenin nasıl kullanılacağını göstermektedir. Aşağıdaki bölümlerde bu parametreler açıklanmaktadır.  
  
 Bkz: [wmain kullanma](../c-language/using-wmain.md) joker karakter sürümünün açıklaması için **ana**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)