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
ms.openlocfilehash: afad5335bedf001329ecb401a8a16c663afb5571
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371584"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Özel Durumlar: MFC Makroları ve C++ Özel Durumlarını Kullanma

Bu makalede, hem MFC özel durum işleme makroları hem de C++ özel durum işleme anahtar kelimelerini kullanan kod yazmak için göz önünde bulundurulması gereken hususlar tartışılmaktadır.

Bu makalede aşağıdaki konular ele:

- [Özel durum anahtar kelimelerini ve makroları karıştırma](#_core_mixing_exception_keywords_and_macros)

- [Catch blokları içinde blokları deneyin](#_core_try_blocks_inside_catch_blocks)

## <a name="mixing-exception-keywords-and-macros"></a><a name="_core_mixing_exception_keywords_and_macros"></a>Özel Durum Anahtar Kelimelerini ve Makroları Karıştırma

MFC özel durum makrolarını ve C++ özel durum anahtar kelimelerini aynı programda karıştırabilirsiniz. Ancak, makrolar kapsam dışına çıktıklarında özel durum nesnelerini otomatik olarak sildiği için MFC makrolarını C++ özel durum anahtar kelimeleriyle aynı blokta karıştıramazsınız, ancak özel durum işleme anahtar kelimelerini kullanan kod kullanılmaz. Daha fazla bilgi için, [özel durumlar makalesine bakın: Özel Durumları Yakalama ve Silme.](../mfc/exceptions-catching-and-deleting-exceptions.md)

Makrolar ve anahtar kelimeler arasındaki temel fark, özel durum kapsam dışına çıktığında makroların yakalanan bir özel durumu "otomatik olarak" silmesidir. Anahtar kelimeleri kullanan kod yok; Yakalama bloğunda yakalanan özel durumlar açıkça silinmelidir. Makroları ve C++ özel durum anahtar kelimelerini karıştırmak, bir özel durum nesnesi silinmediğinde bellek sızıntılarına veya bir özel durum iki kez silindiğinde bozulma yığınına neden olabilir.

Aşağıdaki kod, örneğin, özel durum işaretçisini geçersiz klar:

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

Yürütme "iç" `e` **CATCH** bloğundan geçtiğinde silindiğinde sorun oluşur. **THROW** deyimi yerine **THROW_LAST** makrosu kullanmak "dış" **CATCH** bloğunun geçerli bir işaretçi almasına neden olur:

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

## <a name="try-blocks-inside-catch-blocks"></a><a name="_core_try_blocks_inside_catch_blocks"></a>Catch Bloklar İçindebloklar deneyin

Catch bloğunun içindeki **deneme** bloğunun içinden geçerli **CATCH** özel durumu yeniden atamazsınız. Aşağıdaki örnek geçersizdir:

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

Daha fazla bilgi için özel [durumlar: Özel Durum İçeriklerini İnceleme.](../mfc/exceptions-examining-exception-contents.md)

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
