---
title: "Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler"
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
ms.openlocfilehash: 25095257096efd869e237383c5cd202ae4e602c2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620165"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler

Bu, gelişmiş bir konudur.

MFC sürüm 3,0 ve üzeri sürümlerde, özel durum işleme makroları C++ özel durumlarını kullanacak şekilde değiştirilmiştir. Bu makalede, bu değişikliklerin makroları kullanan varolan kodun davranışını nasıl etkilediği açıklanır.

Bu makalede aşağıdaki konular ele alınmaktadır:

- [Özel durum türleri ve CATCH makrosu](#_core_exception_types_and_the_catch_macro)

- [Özel durumları yeniden oluşturma](#_core_re.2d.throwing_exceptions)

## <a name="exception-types-and-the-catch-macro"></a><a name="_core_exception_types_and_the_catch_macro"></a>Özel durum türleri ve CATCH makrosu

MFC 'nin önceki sürümlerinde, **catch** makrosu bir özel durumun türünü öğrenmek için MFC çalışma zamanı tür bilgilerini kullandı; özel durumun türü, diğer bir deyişle, catch sitesinde belirlenir. Ancak C++ özel durumlarıyla, özel durumun türü her zaman throw sitesinde oluşturulan özel durum nesnesinin türüne göre belirlenir. Bu, oluşturulan nesne işaretçisinin türünün oluşturulan nesnenin türünden farklı olduğu nadir durumda uyumsuzluklar oluşmasına neden olur.

Aşağıdaki örnekte, MFC sürüm 3,0 ve önceki sürümleri arasındaki bu farkın sonucu gösterilmektedir:

[!code-cpp[NVC_MFCExceptions#1](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]

Bu kod sürüm 3,0 ' de farklı davranır çünkü denetim her zaman eşleşen bir özel durum bildirimiyle ilk **catch** bloğuna geçer. Throw ifadesinin sonucu

[!code-cpp[NVC_MFCExceptions#19](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]

, bir olarak `CException*` oluşturulmuş olsa da, olarak oluşturulur `CCustomException` . MFC 2,5 ve önceki sürümlerinde bulunan **catch** makrosu, `CObject::IsKindOf` türü çalışma zamanında test etmek için kullanır. Çünkü ifadesi

[!code-cpp[NVC_MFCExceptions#20](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]

true ise, ilk catch bloğu özel durumu yakalar. Özel durum işleme makrolarını birçok uygulayan C++ özel durumlarını kullanan sürüm 3,0 ' de, ikinci catch bloğu oluşturulan ile eşleşir `CException` .

Bunun gibi bir kod seyrek kullanılır. Genellikle bir özel durum nesnesi genel kabul eden başka bir işleve geçirildiğinde görüntülenir `CException*` , "ön throw" işlemini gerçekleştirir ve son olarak özel durumu oluşturur.

Bu sorunu geçici olarak çözmek için, throw ifadesini işlevinden çağırma koduna taşıyın ve özel durum oluşturulduğu sırada derleyicinin bilinen gerçek türünün bir özel durumunu oluşturun.

## <a name="re-throwing-exceptions"></a><a name="_core_re.2d.throwing_exceptions"></a>Özel durumları yeniden oluşturma

Catch bloğu, yakalandığı özel durum işaretçisini oluşturamaz.

Örneğin, bu kod önceki sürümlerde geçerliyse, ancak 3,0 sürümüne sahip beklenmedik sonuçlara sahip olacak:

[!code-cpp[NVC_MFCExceptions#2](codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]

Catch bloğunda **throw** kullanılması işaretçinin silinmesine neden olur `e` , böylece dış catch sitesinin geçersiz bir işaretçi almasını sağlar. Yeniden oluşturmak için **THROW_LAST** kullanın `e` .

Daha fazla bilgi için bkz. [özel durumlar: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
