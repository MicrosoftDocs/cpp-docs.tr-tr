---
description: 'Hakkında daha fazla bilgi edinin: özel durumlar: MFC özel durum makrolarından dönüştürme'
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
ms.openlocfilehash: 83d4522dff902681e26a2bd098b46fea92bf1c6a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290706"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Özel Durumlar: MFC Özel Durum Makrolarından Dönüştürme

Bu, gelişmiş bir konudur.

Bu makalede, C++ özel durum işleme anahtar sözcüklerini  , ve ' i kullanmak için Microsoft Foundation sınıf makrolarıyla yazılmış mevcut kodların nasıl dönüştürüleceği açıklanır **`try`** **`catch`** **`throw`** . Konu başlıkları şunlardır:

- [Dönüştürme avantajları](#_core_advantages_of_converting)

- [C++ özel durumlarını kullanmak için özel durum makrolarıyla kod dönüştürme](#_core_doing_the_conversion)

## <a name="advantages-of-converting"></a><a name="_core_advantages_of_converting"></a> Dönüştürmenin avantajları

Büyük olasılıkla, MFC sürüm 3,0 ' deki makro uygulamaları ve önceki sürümlerindeki uygulamalar arasındaki farklılıkları farkında olmanız gerektiğine rağmen mevcut kodu dönüştürmeniz gerekmez. Bu farklılıklar ve kod davranışında yapılan değişiklikler, [özel durumlar: sürüm 3,0 ' de özel durum makrolarında yapılan değişiklikler](exceptions-changes-to-exception-macros-in-version-3-0.md)açıklanmaktadır.

Dönüştürmenin başlıca avantajları şunlardır:

- C++ özel durum işleme anahtar sözcüklerini kullanan kod, biraz daha küçük bir şekilde derlenir. EXE veya. Dosyasını.

- C++ özel durum işleme anahtar sözcükleri daha çok yönlüdür: (,, vb.) kopyalanabilen herhangi bir veri türünün özel durumlarını işleyebilir **`int`** **`float`** **`char`** , ancak makrolar yalnızca `CException` Bu sınıftan türetilmiş sınıf ve sınıfların özel durumlarını işler.

Makrolar ve anahtar sözcükler arasındaki önemli fark, "otomatik olarak" makroları kullanan kodun, özel durum kapsam dışına geçtiğinde yakalanan bir özel durumu silmesidir. Anahtar sözcükleri kullanan kod değildir, bu nedenle yakalanan bir özel durumu açıkça silmeniz gerekir. Daha fazla bilgi için bkz. özel durumlar [: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md).

Başka bir farklılık söz dizidir. Makrolar ve anahtar sözcükler için sözdizimi üç yönden farklıdır:

1. Makro bağımsız değişkenleri ve özel durum bildirimleri:

   Bir **catch** makrosu çağrısı aşağıdaki sözdizimine sahiptir:

   **Catch (** *Exception_class*, *exception_object_pointer_name* **)**

   Sınıf adı ve nesne işaretçisi adı arasındaki virgülden dikkat edin.

   Anahtar sözcüğü için özel durum bildirimi **`catch`** şu sözdizimini kullanır:

   **catch (** *exception_type* *exception_name* **)**

   Bu özel durum bildirimi bildirimi, catch bloğunun işlediği özel durum türünü gösterir.

2. Catch bloklarının sınırlandırmaları:

   Makrolar ile, **catch** makrosu (bağımsız değişkenleriyle) ilk catch bloğunu başlatır; **AND_CATCH** makro sonraki catch bloklarından başlar ve **END_CATCH** makro, catch bloklarının dizisini sonlandırır.

   Anahtar kelimeleriyle, **`catch`** anahtar sözcüğü (özel durum bildirimiyle birlikte) her catch bloğuna başlar. **END_CATCH** makroya bir karşılık yoktur; catch bloğu kapanış küme ayracı ile biter.

3. Throw ifadesi:

   Makrolar geçerli özel durumu yeniden oluşturmak için **THROW_LAST** kullanır. **`throw`** Bağımsız değişkeni olmayan anahtar sözcük aynı etkiye sahiptir.

## <a name="doing-the-conversion"></a><a name="_core_doing_the_conversion"></a> Dönüştürme yapılıyor

#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>C++ özel durum işleme anahtar sözcüklerini kullanmak için makroları kullanarak kodu dönüştürmek için

1. MFC **makrolarının** tüm oluşumlarını bulun, **catch**, **AND_CATCH**, **END_CATCH**, **throw** ve **THROW_LAST**.

2. Aşağıdaki makroların tüm yinelemelerini değiştirin veya silin:

   **Dene** (bunu ile Değiştir **`try`** )

   **Yakala** (bunu ile Değiştir **`catch`** )

   **AND_CATCH** (bunu ile Değiştir **`catch`** )

   **END_CATCH** (Sil)

   **Throw** (ile Değiştir **`throw`** )

   **THROW_LAST** (bunu ile Değiştir **`throw`** )

3. Makro bağımsız değişkenlerini geçerli özel durum bildirimleri oluşturacak şekilde değiştirin.

   Örneğin, Değiştir

   [!code-cpp[NVC_MFCExceptions#6](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]

   şöyle değiştirin:

   [!code-cpp[NVC_MFCExceptions#7](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]

4. Özel durum nesnelerini gerektiği şekilde silmesi için catch bloklarından kodu değiştirin. Daha fazla bilgi için bkz. özel durumlar [: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md).

MFC özel durum makroları kullanılarak özel durum işleme kodu örneği aşağıda verilmiştir. Aşağıdaki örnekteki kod makroları kullandığından, özel durumun `e` otomatik olarak silindiğini unutmayın:

[!code-cpp[NVC_MFCExceptions#8](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]

Sonraki örnekteki kod C++ özel durum anahtar sözcüklerini kullanır, bu nedenle özel durumun açıkça silinmesi gerekir:

[!code-cpp[NVC_MFCExceptions#9](codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]

Daha fazla bilgi için bkz. [özel durumlar: MFC makroları ve C++ özel durumlarını kullanma](exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)<br/>
