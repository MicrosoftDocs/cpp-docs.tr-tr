---
title: 'Özel Durumlar: MFC Makroları ve C++ Özel Durumlarını Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: d669c58da04a1cd0ead424d93f6fad6adcd4c56c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622736"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Özel Durumlar: MFC Makroları ve C++ Özel Durumlarını Kullanma

Bu makalede hem MFC özel durum işleme makrolarını hem de C++ özel durum işleme anahtar sözcüklerini kullanan kod yazma konuları anlatılmaktadır.

Bu makalede aşağıdaki konular ele alınmaktadır:

- [Özel durum anahtar sözcüklerini ve makroları karıştırma](#_core_mixing_exception_keywords_and_macros)

- [Catch blokları içinde blokları deneyin](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>Özel durum anahtar sözcüklerini ve makroları karıştırma

MFC özel durum makrolarını ve C++ özel durum anahtar sözcüklerini aynı programda karıştırabilirsiniz. Ancak, özel durum işleme anahtar sözcüklerini kullanan kod olmasa da, makrolar özel durum nesnelerini otomatik olarak siltiğinden, MFC makrolarını aynı bloktaki C++ özel durum anahtar sözcükleriyle karıştıramazsınız. Daha fazla bilgi için bkz. özel durumlar [: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md).

Makrolar ve anahtar sözcükler arasındaki temel fark, özel durum kapsam dışına geçtiğinde makroların "otomatik olarak" yakalandığı bir özel durumu silmesi olur. Anahtar sözcükleri kullanan kod değildir; bir catch bloğunda yakalanan özel durumların açıkça silinmesi gerekir. Makrolar ve C++ özel durum anahtar sözcüklerini karıştırma, bir özel durum nesnesi silinmediği zaman, veya iki kez bir özel durum silindiğinde yığın bozulması nedeniyle bellek sızıntılarına neden olabilir.

Aşağıdaki kod, örneğin, özel durum işaretçisini geçersiz kılar:

[!code-cpp[NVC_MFCExceptions#10](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Bu sorun, `e` yürütme "iç" **catch** bloğunun dışına çıktığında silindiği için oluşur. **Throw** ifadesinin yerine **THROW_LAST** makrosunu kullanmak, "dış" **catch** bloğunun geçerli bir işaretçi almasına neden olur:

[!code-cpp[NVC_MFCExceptions#11](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>Catch blokları Içinde blokları deneyin

Geçerli özel durumu bir **catch** bloğu içinde olan **TRY** bloğu içinden yeniden oluşturamazsınız. Aşağıdaki örnek geçersiz:

[!code-cpp[NVC_MFCExceptions#12](codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Daha fazla bilgi için bkz. [özel durumlar: özel durum Içeriklerini İnceleme](exceptions-examining-exception-contents.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
