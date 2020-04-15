---
title: 'Özel Durumlar: MFC Özel Durum Makrolarından Dönüştürme'
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
ms.openlocfilehash: 330f66b1f46542082637645ad53da016b434d4a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372024"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Özel Durumlar: MFC Özel Durum Makrolarından Dönüştürme

Bu gelişmiş bir konudur.

Bu makalede, Microsoft Foundation Class makroları ile yazılmış varolan kodun nasıl dönüştürülür - **TRY**, **CATCH**, **THROW**, ve benzeri — C++ özel durum işleme anahtar kelimelerini kullanmak için **deneyin,** **yakalayın**ve **atın**. Konu başlıkları şunlardır:

- [Dönüşüm avantajları](#_core_advantages_of_converting)

- [C++ özel durumlarını kullanmak için özel durum makroları ile kodu dönüştürme](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a>Dönüştürmenin Avantajları

MFC sürüm 3.0'daki makro uygulamaları ile önceki sürümdeki uygulamalar arasındaki farkların farkında olmanız gerekirken, büyük olasılıkla varolan kodu dönüştürmeniz gerekmez. Bu farklar ve kod davranışındaki sonraki değişiklikler [Özel Durumlar:Sürüm 3.0'daki Özel Durum Makrolarında Yapılan Değişiklikler.](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

Dönüştürmenin başlıca avantajları şunlardır:

- C++ özel durum işleme anahtar kelimelerini kullanan kod biraz daha küçük. EXE veya . Dll.

- C++ özel durum işleme anahtar kelimeleri daha çok yönlüdür: Kopyalanabilen herhangi bir veri türünün özel durumlarını **(int,** **float,** `CException` **char,** vb.) işlerken, makrolar yalnızca sınıf ve ondan türetilen sınıfların özel durumlarını işler.

Makrolar ve anahtar kelimeler arasındaki en büyük fark, makroları kullanan kodun özel durum kapsam dışına çıktığında yakalanan bir özel durumu "otomatik olarak" silmesidir. Anahtar kelimeleri kullanan kod kullanılmaz, bu nedenle yakalanan bir özel durumu açıkça silmeniz gerekir. Daha fazla bilgi için, [özel durumlar makalesine bakın: Özel Durumları Yakalama ve Silme.](../mfc/exceptions-catching-and-deleting-exceptions.md)

Başka bir fark sözdizimidir. Makrolar ve anahtar kelimeler için sözdizimi üç açıdan farklıdır:

1. Makro bağımsız değişkenleri ve özel durum bildirimleri:

   Catch **CATCH** makro çağırma aşağıdaki sözdizimi vardır:

   **CATCH(** *exception_class*, *exception_object_pointer_name* **)**

   Sınıf adı ve nesne işaretçiadı adı arasındaki virgüle dikkat edin.

   **Catch** anahtar sözcüğünün özel durum bildiriminde şu sözdizimi kullanır:

   **yakalamak (** *exception_type* *exception_name* **)**

   Bu özel durum bildirimi bildirimi, catch bloğu işlemi özel durum türünü gösterir.

2. Catch bloklarının sınırlandırılması:

   Makrolarla **CATCH** makrosu (bağımsız değişkenleriyle) ilk catch bloğunu başlatır; **AND_CATCH** makro sonraki catch blokları başlar ve **END_CATCH** makro catch blokları dizisini sona erdirir.

   Anahtar kelimelerle, **catch** anahtar kelimesi (özel durum bildirimi yle) her catch bloğunu başlatır. **END_CATCH** makronun muadili yoktur; catch bloğu kapanış ayracı ile sona erer.

3. Atma ifadesi:

   Makrolar, geçerli özel durumu yeniden atmak için **THROW_LAST** kullanır. Hiçbir bağımsız değişken ile **throw** anahtar kelimesi, aynı etkiye sahiptir.

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a>Dönüşüm yapma

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>C++ özel durum işleme anahtar kelimelerini kullanmak için makroları kullanarak kodu dönüştürmek için

1. MFC makrolarının tüm oluşumlarını bulun **TRY**, **CATCH**, **AND_CATCH**, **END_CATCH**, **THROW**, ve **THROW_LAST**.

2. Aşağıdaki makroların tüm oluşumlarını değiştirin veya silin:

   **TRY** **(Try**ile değiştirin)

   **CATCH** **(Catch**ile değiştirin )

   **AND_CATCH** **(Catch**ile değiştirin )

   **END_CATCH** (Silin)

   **THROW** **(Throw**ile değiştirin )

   **THROW_LAST** **(atmak**ile değiştirin )

3. Makro bağımsız değişkenlerini geçerli özel durum bildirimleri oluşturacak şekilde değiştirin.

   Örneğin, değişiklik

   [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   -

   [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Parolayı, özel durum nesnelerini gerektiği gibi silebilmek için değiştirin. Daha fazla bilgi için, [özel durumlar makalesine bakın: Özel Durumları Yakalama ve Silme.](../mfc/exceptions-catching-and-deleting-exceptions.md)

Burada, MFC özel durum makrolarını kullanan özel durum işleme kodunun bir örneği verilmiştir. Aşağıdaki örnekteki kod makroları kullandığından, özel `e` durum otomatik olarak silinir:

[!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

Sonraki örnekteki kod C++ özel durum anahtar kelimelerini kullanır, bu nedenle özel durum açıkça silinmelidir:

[!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Daha fazla bilgi için [bkz: MFC Makroları ve C++ Özel Durumları kullanma.](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)<br/>
