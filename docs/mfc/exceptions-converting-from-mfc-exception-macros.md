---
title: 'Özel durumlar: MFC özel durum makrolarından dönüştürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a386de558730e12bb8cf40da250c1d04dd4ff37a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931124"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Özel Durumlar: MFC Özel Durum Makrolarından Dönüştürme
Bu gelişmiş bir konudur.  
  
 Bu makalede, Microsoft Foundation Class makroları ile yazılan varolan kod dönüştürmek açıklanmaktadır — **deneyin**, **CATCH**, **THROW**ve benzeri — C++ özel durum işleme kullanmak için anahtar sözcükler **deneyin**, **catch**, ve **throw**. Konular şunlardır:  
  
-   [Dönüştürme avantajları](#_core_advantages_of_converting)  
  
-   [C++ özel durumlarını kullanmak için özel durum makroları koduyla dönüştürme](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> Dönüştürme avantajları  
 MFC sürüm 3.0 makrosu uygulamalarında ve önceki sürümleri uygulamalarında arasındaki farklar bilincinde olmanız gereken olsa da, büyük olasılıkla var olan kodu dönüştürmek gerekmez. Bu farklılıklar ve sonraki kod davranış değişiklikleri ele alınmıştır [özel durumlar: sürüm 3.0 özel durum makrolarındaki değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
 Dönüştürme asıl avantajları şunlardır:  
  
-   C++ özel durum işleme anahtar sözcükleri kullanan kodu biraz daha küçük derler. EXE veya. DLL.  
  
-   C++ özel durum işleme anahtar sözcükleri daha kullanışlıdır: kopyalanabilmesi için herhangi bir veri türü özel durumları işleyebilir (**int**, **float**, **char**, vb.), ancak Makroları yalnızca sınıfının özel durumları işleme `CException` ve ondan türetilmiş sınıfları.  
  
 Makrolar ve anahtar sözcükler arasındaki en önemli fark, özel durum kapsam dışına çıktığında Yakalanan özel durum makroları "Otomatik" kullanarak kod siler ' dir. Anahtar sözcükler yok, yakalanan özel durum açıkça silmeniz gerekir böylece kullanan kod. Daha fazla bilgi için bkz: [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Sözdizimi başka bir farktır. Makrolar ve anahtar sözcükler sözdizimi üç yönden farklıdır:  
  
1.  Makro bağımsız ve özel durum bildirimleri:  
  
     A **CATCH** makrosu çağırma aşağıdaki sözdizimi vardır:  
  
     **CATCH (** *exception_class*, *exception_object_pointer_name* **)**  
  
     Sınıf adı ve nesne işaretçisi adı arasında virgül dikkat edin.  
  
     Özel durum bildirimi **catch** anahtar sözcüğü bu söz dizimini kullanır:  
  
     **catch (** *exception_type* *exception_name ***)**  
  
     Bu özel durum bildirimi deyimi catch özel durum türünü gösterir tanıtıcıları engelleyin.  
  
2.  Catch blokları ayırma:  
  
     Makroları ile **CATCH** makrosu (bağımsız değişkenleri ile) başlayan ilk catch bloğu; **AND_CATCH** makrosu sonraki catch bloklarını başlar ve **END_CATCH** makrosu catch blokları dizisini sonlandırır.  
  
     Anahtar sözcükler **catch** anahtar sözcüğü (ile özel durum bildiriminden) her catch bloğu başlar. Hiçbir karşılık gelen yoktur **END_CATCH** makrosu; kendi kapatılan parantez ile biter engelleme yakalama.  
  
3.  Throw deyimi:  
  
     Makroları kullanma **THROW_LAST** geçerli özel durumun yeniden oluşturulacak. **Throw** hiçbir bağımsız değişkeniyle anahtar sözcüğü ile aynı etkiye sahiptir.  
  
##  <a name="_core_doing_the_conversion"></a> Dönüştürme yapmak  
  
#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>C++ özel durum işleme anahtar sözcükleri kullanmak için makroları kullanarak kod dönüştürmek için  
  
1.  MFC makroları tüm örneklerini bulun **deneyin**, **CATCH**, **AND_CATCH**, **END_CATCH**, **THROW**, ve **THROW_LAST**.  
  
2.  Değiştirin veya aşağıdaki makroları tüm oluşumlarını Sil:  
  
     **DENEYİN** (bunların yerine **deneyin**)  
  
     **CATCH** (bunların yerine **catch**)  
  
     **AND_CATCH** (bunların yerine **catch**)  
  
     **END_CATCH** (silme)  
  
     **THROW** (bunların yerine **throw**)  
  
     **THROW_LAST** (bunların yerine **throw**)  
  
3.  Geçerli özel durum bildirimleri form makrosu bağımsız değişkenleri değiştirin.  
  
     Örneğin, değiştirme  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     to  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  Catch blokları kodda özel durum nesneleri gerekirse siler şekilde değiştirin. Daha fazla bilgi için bkz: [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 MFC özel durum makroları kullanarak özel durum işleme kod bir örneği burada verilmiştir. Aşağıdaki örnek kodda özel durum makroları kullandığından unutmayın `e` otomatik olarak silinir:  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 Sonraki örnek kodda özel durum açıkça silinmelidir C++ özel durum anahtar sözcükleri kullanır:  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 Daha fazla bilgi için bkz: [özel durumlar: kullanarak MFC makroları ve C++ özel durumlarını](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

