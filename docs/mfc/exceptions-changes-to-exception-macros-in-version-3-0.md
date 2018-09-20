---
title: "Özel durumlar: Sürüm 3. 0'da özel durum makrolarındaki değişiklikler | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8829c018e51b81c0997092312e3e058d3086665b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417039"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler

Bu gelişmiş bir konudur.

MFC sürüm 3.0 ve sonraki sürümlerinde, C++ özel durumlarını kullanmak için özel durum işleme makroları değiştirildi. Bu makalede, bu değişiklikleri makroları kullanan mevcut kodu davranışını nasıl etkileyebileceğini söyler.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Özel durum türlerini ve CATCH makrosu](#_core_exception_types_and_the_catch_macro)

- [Yeniden özel durumları atma](#_core_re.2d.throwing_exceptions)

##  <a name="_core_exception_types_and_the_catch_macro"></a> Özel durum türlerini ve CATCH makrosu

MFC, önceki sürümlerinde **CATCH** makrosu MFC çalışma zamanı türü bilgileri özel durum türünü belirlemek için kullanılan dize; özel durumun türü, diğer bir deyişle, catch sitede belirlenir. İle C++ özel durumlarını, ancak özel durumun türü her zaman throw sitede harekete geçirilen özel durum nesnesi türüne göre belirlenir. Burada oluşturulan nesneye bir işaretçi türü oluşturulan nesnenin türünden farklı nadir durumda bu uyumsuzlukların neden olur.

Aşağıdaki örnekte, sonucu MFC sürüm 3.0 ve önceki sürümleri arasındaki bu fark gösterilmektedir:

[!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

Denetimi her zaman için ilk geçirdiği için bu kod sürüm 3.0 farklı davranır **catch** bloğu ile eşleşen bir özel durum bildirimi. Throw ifadesi sonucu

[!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

olarak oluşturulan bir `CException*`rağmen olarak oluşturulmuş bir `CCustomException`. **CATCH** MFC sürüm 2.5 ve önceki kullanımlar makroda `CObject::IsKindOf` çalışma zamanında tür test etmek için. Olduğundan ifade

[!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

ilk yakalama bloğu özel durumu yakalar true olur. İkinci yakalama bloğunun özel durum işleme makroları birçoğu uygulamak için C++ özel durumlarını kullanan sürüm 3. 0, oluşturulan eşleşen `CException`.

Bu kodu değildir. Özel durum nesnesine genel kabul eden başka bir işleve geçirildiğinde genellikle görünür `CException*`, "ön throw" işleme gerçekleştirir ve son özel durum oluşturur.

Bu sorunu gidermek için throw ifadesi fonksiyonu çağıran koda taşıyın ve derleyiciye özel durumu oluşturan zamanında bilinen gerçek türünde bir özel durum atar.

##  <a name="_core_re.2d.throwing_exceptions"></a> Yeniden özel durumları atma

Bir catch bloğu, yakalanan aynı özel durum işaretçisi nelze vyvolat.

Örneğin, bu kod önceki sürümlerinde geçerli, ancak sahip sürüm 3.0 ile beklenmeyen sonuçlar:

[!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Kullanarak **THROW** catch bloğu işaretçi neden `e` silinecek, böylece dış catch site geçersiz bir işaretçi alır. Kullanım **THROW_LAST** yeniden harekete geçirileceğini `e`.

Daha fazla bilgi için [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

