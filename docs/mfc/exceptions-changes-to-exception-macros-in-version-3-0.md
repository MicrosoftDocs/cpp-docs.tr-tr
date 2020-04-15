---
title: "Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler"
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 82320b0c7ccd6766e016f0437633339f8f8f61d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365489"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler

Bu gelişmiş bir konudur.

MFC sürüm 3.0 ve sonraki sürümlerde, özel durum işleme makroları C++ özel durumlarını kullanacak şekilde değiştirildi. Bu makalede, bu değişikliklerin makroları kullanan varolan kodun davranışını nasıl etkileyebileceği açıklanmıştır.

Bu makalede aşağıdaki konular ele:

- [Özel durum türleri ve CATCH makrosu](#_core_exception_types_and_the_catch_macro)

- [Özel durumları yeniden atma](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>Özel Durum Türleri ve CATCH Makrosu

MFC'nin önceki sürümlerinde **CATCH** makrosu, bir özel durum türünü belirlemek için MFC çalışma zamanı türü bilgilerini kullansın; istisnanın türü, başka bir deyişle, yakalama yerinde belirlenir. Ancak, C++ özel durumları ile, özel durum türü her zaman atılan özel durum nesnesinin türüne göre atma yerinde belirlenir. Bu, atılan nesneye işaretçi türünün atılan nesnenin türünden farklı olduğu nadir durumlarda uyumsuzluklara neden olur.

Aşağıdaki örnek, MFC sürüm 3.0 ve önceki sürümler arasındaki bu farkın sonucunu göstermektedir:

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

Denetim her zaman eşleşen bir özel durum bildirimi ile ilk **catch** bloğuna geçtiğinden, bu kod sürüm 3.0'da farklı şekilde davranın. Atma ifadesinin sonucu

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

olarak `CException*`atılırsa, bir `CCustomException`olarak inşa edilmiş olsa bile . MFC sürümleri 2.5 ve önceki `CObject::IsKindOf` **CATCH** makro çalışma zamanında türünü test etmek için kullanır. Çünkü ifade

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

doğrudur, ilk catch bloğu özel durum yakalar. Özel durum işleme makrolarının çoğunu uygulamak için C++ özel durumlarını kullanan sürüm 3.0'da, ikinci catch bloğu atılanlarla `CException`eşleşir.

Bunun gibi kodlar nadirdir. Genellikle bir özel durum nesnesi genel `CException*`kabul eden başka bir işleve geçirildiğinde görünür, "ön atma" işleme gerçekleştirir ve son olarak özel durum atar.

Bu sorunu çözmek için, atma ifadesini işlevden arama koduna taşıyın ve özel durum oluşturulduğu anda derleyicitarafından bilinen gerçek türden bir özel durum atın.

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>Özel Durumları Yeniden Atma

Catch bloğu, yakaladığı aynı özel durum işaretçisini atamaz.

Örneğin, bu kod önceki sürümlerde geçerliydi, ancak sürüm 3.0 ile beklenmeyen sonuçlar doğurur:

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Catch bloğunda **THROW'nin** `e` kullanılması işaretçinin silinmesine neden olur, böylece dış catch sitesi geçersiz bir işaretçi alır. Yeniden **THROW_LAST** atmak `e`için THROW_LAST kullanın.

Daha fazla bilgi için özel [durumlar: Özel Durumları Yakalama ve Silme](../mfc/exceptions-catching-and-deleting-exceptions.md)bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
