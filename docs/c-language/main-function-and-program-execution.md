---
description: 'Daha fazla bilgi edinin: Main Işlevi ve program yürütme'
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
ms.openlocfilehash: 00fb10526b558631c024366c09a773363bd81683
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257088"
---
# <a name="main-function-and-program-execution"></a>main İşlevi ve Program Yürütme

Her C programının **Main** olarak adlandırılması gereken birincil (ana) işlevi vardır. Kodunuz Unicode programlama modeline uygunsa **ana**, **wmain**'in geniş karakterli sürümünü kullanabilirsiniz. **Main** işlevi program yürütmesi için başlangıç noktası işlevi görür. Genellikle çağrıları programdaki diğer işlevlere yönlendirerek program yürütmesini denetler. Program genellikle **Main**'in sonunda yürütmeyi durduruyor, ancak çeşitli nedenlerle programın diğer noktalarında sonlandırılabilir. Bazen belirli bir hata algılandığında, programı sonlandırılmaya zorlamak isteyebilirsiniz. Bunu yapmak için **Exit** işlevini kullanın. Bilgi için *çalışma zamanı kitaplığı başvurusuna* ve [Çıkış](../c-runtime-library/reference/exit-exit-exit.md) işlevini kullanarak bir örneğe bakın.

## <a name="syntax"></a>Syntax

```
main( int argc, char *argv[ ], char *envp[ ] )
```

## <a name="remarks"></a>Açıklamalar

Kaynak programının içerisindeki işlevler, bir veya daha fazla belirli görevi gerçekleştirir. **Main** işlevi ilgili görevlerini gerçekleştirmek için bu işlevleri çağırabilir. **Main** başka bir işlevi çağırdığında yürütme denetimini işleve geçirir, böylece yürütme işlevdeki ilk deyimden başlar. Bir işlev, bir  **`return`** ifade yürütüldüğünde veya işlevin sonuna ulaşıldığında denetimi Main öğesine döndürür.

Parametrelere sahip olmak için **Main** dahil herhangi bir işlevi bildirebilirsiniz. "Parametre" veya "biçimsel parametre" terimi, işleve geçirilen bir değeri alan tanımlayıcı anlamına gelir. Bağımsız değişkenleri parametrelere geçirme hakkında bilgi için bkz. [Parametreler](../c-language/parameters.md) . Bir işlev diğerini çağırdığında, çağrılan işlev çağıran işlevden parametrelerine yönelik değerleri alır. Bu değerlere "bağımsız değişkenler" adı verilir. Aşağıdaki biçimi kullanarak komut satırından bağımsız değişkenleri alabilmesi için, biçimsel parametreleri **Main** 'e bildirebilirsiniz:

**Ana** işleve bilgi geçirmek istediğinizde, parametreler genellikle `argc` ve `argv` olarak adlandırılır, ancak C derleyicisi bu adları gerektirmez. `argc` ve `argv` türleri, C dili tarafından tanımlanır. Geleneksel olarak, üçüncü bir parametre **Main**'e geçirilirse, bu parametre adlandırılır `envp` . Bu bölümdeki diğer örnekler, komut satırı bağımsız değişkenlerine erişmek için bu üç parametrenin nasıl kullanılacağını göstermektedir. Aşağıdaki bölümlerde bu parametreler açıklanmaktadır.

**Ana** öğesinin geniş karakterli sürümünün açıklaması için bkz. [wmain kullanma](../c-language/using-wmain.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Main işlevi ve komut satırı bağımsız değişkenleri (C++)](../cpp/main-function-command-line-args.md)\
[C Command-Line bağımsız değişkenlerini ayrıştırma](../c-language/parsing-c-command-line-arguments.md)
