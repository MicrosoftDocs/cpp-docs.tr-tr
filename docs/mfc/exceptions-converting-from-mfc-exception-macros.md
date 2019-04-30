---
title: 'Özel durumlar: MFC özel durum makrolarından dönüştürme'
ms.date: 08/27/2018
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
ms.openlocfilehash: 59b83438d5341fd6a139af64a2f365a739438741
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394513"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Özel durumlar: MFC özel durum makrolarından dönüştürme

Bu gelişmiş bir konudur.

Bu makalede, Microsoft Foundation Class makroları ile yazılan mevcut kod dönüştürmek açıklanmaktadır — **deneyin**, **CATCH**, **THROW**ve benzeri — C++ özel durum işleme kullanmak için anahtar sözcükler **deneyin**, **catch**, ve **throw**. Konular şunlardır:

- [Dönüştürme avantajları](#_core_advantages_of_converting)

- [Dönüştürme kodu ile C++ özel durumlarını kullanmak için özel durum makroları](#_core_doing_the_conversion)

##  <a name="_core_advantages_of_converting"></a> Dönüştürme avantajları

MFC sürüm 3.0 makrosu uygulamalarında önceki sürümlerde uygulamaları arasındaki farkların farkında olmanız olsa da, büyük olasılıkla mevcut kodu dönüştürmek gerekmez. Bu farklılıklar ve sonraki kod davranışında değişiklik ele alınmıştır [özel durumlar: Sürüm 3. 0'da özel durum makrolarındaki değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

Dönüştürme asıl avantajları şunlardır:

- C++ özel durum işleme anahtar sözcükleri kullanan kod biraz daha küçük derler. EXE veya. DLL.

- C++ Daha ayrıntılı özel durum işleme anahtar sözcükler: Bunlar kopyalanabilir herhangi bir veri türü özel durumları işleyebilir (**int**, **float**, **char**, vb.) makroları yalnızca sınıfın özel durumları işlemek bilgileriyse `CException` ve ondan türetilen sınıflar.

Makrolar ve anahtar sözcükler arasındaki en önemli fark, özel durum kapsam dışına çıktığında "Otomatik" makroları kullanarak kod özel durum yakalandı siler ' dir. Özel durum yakalandı açıkça silmeniz gerekir böylece anahtar sözcükleri yok, kod kullanarak. Daha fazla bilgi için bkz [özel durumlar: Yakalama ve özel durumları silme](../mfc/exceptions-catching-and-deleting-exceptions.md).

Söz dizimi başka bir farktır. Makrolar ve anahtar sözcükler için söz dizimi üç yönden farklıdır:

1. Makro bağımsız değişkenler ve özel durum bildirimi:

   A **CATCH** makro çağrısı sözdizimine sahiptir:

   **CATCH (** *exception_class*, *exception_object_pointer_name* **)**

   Sınıf adı ve nesne işaretçisi adı arasında virgül dikkat edin.

   Özel durum bildirimi **catch** anahtar sözcüğü, bu sözdizimini kullanır:

   **catch (** *exception_type* *exception_name* **)**

   Bu özel durum bildirimi deyimi catch özel durum türünü gösterir tanıtıcıları engelleyin.

2. Catch blokları ayırma:

   Makrolar ile **CATCH** makrosu (bağımsız değişkenlerinden ile) başlayan ilk catch bloğu; **AND_CATCH** makrosu sonraki catch blokları başlar ve **END_CATCH** makrosu catch blokları dizisini sonlandırır.

   Anahtar sözcükleri içeren **catch** anahtar sözcüğü (ile kendi özel durum bildirimi) her bir catch bloğu başlar. İçin hiçbir karşılığı yoktur **END_CATCH** makrosu; yakalama, kapanış küme ayracı ile biter engelleyin.

3. Throw ifadesi:

   Makroları kullanma **THROW_LAST** geçerli özel durumu yeniden harekete geçirerek. **Throw** anahtar sözcüğü, hiçbir bağımsız değişken ile aynı etkiye sahiptir.

##  <a name="_core_doing_the_conversion"></a> Dönüştürme yapmak

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>C++ özel durum işleme anahtar kelimeler kullanmanız makroları kullanarak kod dönüştürmek için

1. MFC makroları tüm oluşumlarını bulmak **deneyin**, **CATCH**, **AND_CATCH**, **END_CATCH**, **THROW**, ve **THROW_LAST**.

2. Aşağıdaki makroları tüm örneklerini silin veya değiştirin:

   **DENEYİN** (ile değiştirirsiniz **deneyin**)

   **CATCH** (ile değiştirirsiniz **catch**)

   **AND_CATCH** (ile değiştirirsiniz **catch**)

   **END_CATCH** (Sil)

   **THROW** (ile değiştirirsiniz **throw**)

   **THROW_LAST** (ile değiştirirsiniz **throw**)

3. Makro bağımsız değişkeni geçerli bir özel durum bildirimleri oluşturdukları şekilde değiştirin.

   Örneğin, değiştirme

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   to

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Catch blokları kodda özel durum nesneleri gerekirse siler şekilde değiştirin. Daha fazla bilgi için bkz [özel durumlar: Yakalama ve özel durumları silme](../mfc/exceptions-catching-and-deleting-exceptions.md).

MFC özel durum makroları kullanarak özel durum işleme kod örneği aşağıda verilmiştir. Aşağıdaki örnek kodda özel durum makroları kullandığından unutmayın `e` otomatik olarak silinir:

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

Sonraki örnek kodda özel durum açıkça silinmelidir C++ özel durum anahtar sözcükleri kullanır:

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Daha fazla bilgi için [özel durumlar: MFC makroları ve C++ özel durumlarını kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)<br/>
