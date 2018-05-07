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
ms.openlocfilehash: 92d1691f9a61a11dc4d9dfe7e869ccb7899746bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Özel Durumlar: Sürüm 3.0'da Özel Durum Makrolarındaki Değişiklikler
Bu gelişmiş bir konudur.  
  
 Sürüm 3.0 ve sonraki MFC'de C++ özel durumlarını kullanmak için özel durum işleme makroları değiştirildi. Bu makalede, bu değişiklikleri makrolar kullanan var olan kodu davranışını nasıl etkileyebileceğini söyler.  
  
 Bu makalede aşağıdaki konuları içerir:  
  
-   [Özel durum türleri ve CATCH makrosu](#_core_exception_types_and_the_catch_macro)  
  
-   [Yeniden özel durumları atma](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> Özel durum türleri ve CATCH makrosu  
 MFC, önceki sürümlerinde **CATCH** makrosu MFC çalışma zamanı türü bilgileri özel durum türü belirlemek için kullanılır; özel durum türü, diğer bir deyişle, yakalama sitede belirlenir. C++ özel durum dışında ancak, özel durumun türü her zaman throw sitede oluşturulan özel durum nesnesi türü tarafından belirlenir. Bu uyumsuzlukları burada atılmış nesnesine işaretçi türü atılmış nesne türünden farklı nadir durumda neden olur.  
  
 Aşağıdaki örnekte, MFC sürüm 3.0 ve önceki sürümleri arasındaki bu farklılık sonucu gösterilmektedir:  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 Denetim her zaman için ilk atladığı için bu kodu farklı sürüm 3.0 davranır **catch** eşleşen bir özel durum bildirimi with bloğu. Throw deyimi sonucu  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 olarak oluşturulan bir **CException\*** rağmen olarak oluşturulan bir **CCustomException**. **CATCH** makrosu MFC sürüm 2.5 ve önceki kullanır `CObject::IsKindOf` çalışma zamanında tür test etmek için. Çünkü ifade  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 ilk yakalama bloğunun özel durumu yakalar, geçerlidir. Özel durum işleme makroları çoğunu uygulamak için C++ özel durumlarını kullanan sürüm 3. 0, İkinci catch bloğu atılmış eşleşen `CException`.  
  
 Bu gibi sık karşılaşılan bir durum kodudur. Bir özel durum nesnesi genel kabul eden başka bir işleve geçirildiğinde genellikle görünür **CException\***, "ön throw" işleme gerçekleştirir ve son olarak özel durum oluşturur.  
  
 Bu sorunu geçici olarak çözmek için throw deyimi işlevinden çağıran kodu taşımak ve özel durum oluşturdu aynı anda derleyiciye bilinen gerçek türünde bir özel durum atar.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> Yeniden özel durumları atma  
 Catch bloğu, yakalanan aynı özel durum işaretçi oluşturulamıyor.  
  
 Örneğin, bu kod önceki sürümlerde geçerli, ancak sahip sürüm 3.0 ile beklenmeyen sonuçlar:  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 Kullanarak **THROW** catch bloğu işaretçinin neden `e` silinmesi, böylece dış catch site geçersiz bir işaretçi alırsınız. Kullanım `THROW_LAST` yeniden vermesini `e`.  
  
 Daha fazla bilgi için bkz: [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

