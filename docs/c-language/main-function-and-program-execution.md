---
title: main İşlevi ve Program Yürütme
ms.date: 11/04/2016
helpviewer_keywords:
- program startup [C++]
- entry points, program
- main function, program execution
- startup code, main function
- main function
- programs [C++], terminating
ms.assetid: 5984f1bd-072d-4e06-8640-122fb1454401
ms.openlocfilehash: d16f8a5b7b6b23ad90aad886bbb9654e706549cb
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151046"
---
# <a name="main-function-and-program-execution"></a>main İşlevi ve Program Yürütme

Her C programında adlandırılması gereken birincil (ana) bir işlev olan **ana**. Kodunuz Unicode programlama modelini kullanıyorsa, geniş karakter sürümünü kullanabilirsiniz **ana**, **wmain**. **Ana** program yürütme için başlangıç noktası işlevi görür. Genellikle çağrıları programdaki diğer işlevlere yönlendirerek program yürütmesini denetler. Bir program, genellikle sonunda yürütme durdurur **ana**, ancak çeşitli nedenlerle programın diğer noktalarında sonlandırabilirsiniz. Bazen belirli bir hata algılandığında, programı sonlandırılmaya zorlamak isteyebilirsiniz. Bunu yapmak için **çıkmak** işlevi. Bkz: *çalışma zamanı kitaplığı başvurusu* ilişkin bilgiler ve bir örnek kullanarak [çıkmak](../c-runtime-library/reference/exit-exit-exit.md) işlevi.

## <a name="syntax"></a>Sözdizimi

```
main( int argc, char *argv[ ], char *envp[ ] )
```

## <a name="remarks"></a>Açıklamalar

Kaynak programının içerisindeki işlevler, bir veya daha fazla belirli görevi gerçekleştirir. **Ana** işlevi, ilgili görevlerini gerçekleştirmek için bu işlevleri çağırabilir. Zaman **ana** başka bir işlev çağırır yürütme işlevdeki ilk deyimde başlayabilmesi için yürütme denetimini işleve geçirir. Denetim için bir işlev döndürür **ana** olduğunda bir `return` deyimi yürütüldüğünde veya işlevin sonuna ulaşıldığında.

Herhangi bir işlevi bildirebilir dahil olmak üzere **ana**parametrelere sahip olacak şekilde. "Parametre" veya "biçimsel parametre" terimi, işleve geçirilen bir değeri alan tanımlayıcı anlamına gelir. Bkz: [parametreleri](../c-language/parameters.md) bağımsız değişkenleri parametrelere geçirme hakkında bilgi. Bir işlev diğerini çağırdığında, çağrılan işlev çağıran işlevden parametrelerine yönelik değerleri alır. Bu değerlere "bağımsız değişkenler" adı verilir. Biçimsel parametreler bildirebilirsiniz **ana** bağımsız değişkenleri komut satırından şu biçimi kullanarak alabilmesi:

Bilgi aktarmak istediğinizde **ana** gibi parametreleri işlevi, geleneksel olarak adlandırılan `argc` ve `argv`, C derleyicisi bu adlar gerekli olmasa da. 
  `argc` ve `argv` türleri, C dili tarafından tanımlanır. Geleneksel olarak, üçüncü parametresi geçirilir **ana**, bu parametrenin adlı `envp`. Bu bölümdeki diğer örnekler, komut satırı bağımsız değişkenlerine erişmek için bu üç parametrenin nasıl kullanılacağını göstermektedir. Aşağıdaki bölümlerde bu parametreler açıklanmaktadır.

Bkz: [wmain kullanma](../c-language/using-wmain.md) geniş karakter sürümünü açıklamasını **ana**.

## <a name="see-also"></a>Ayrıca bkz.

[Ana: Program başlatma](../cpp/main-program-startup.md)<br/>
[C Komut Satırı Bağımsız Değişkenlerini Ayrıştırma](../c-language/parsing-c-command-line-arguments.md)
