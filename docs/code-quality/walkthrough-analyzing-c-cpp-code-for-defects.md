---
title: 'İzlenecek yol: hatalar için C/C++ kodunu analiz etme'
description: Visual Studio 'da Microsoft C++ ile Kod analizini nasıl kullanacağınızı gösterir.
ms.date: 04/14/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.openlocfilehash: 65da18f5f6d1972276f1cb8e306e82314282e40a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227718"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>İzlenecek yol: hatalar için C/C++ kodunu analiz etme

Bu izlenecek yol, olası kod kusurları için C/C++ kodunun nasıl çözümlendiğini gösterir. C/C++ kodu için kod çözümleme araçları ' nı kullanır.

Bu izlenecek yolda şunları yapmanız gerekir:

- Yerel kodda Kod analizini Çalıştır.
- Kod hatası uyarılarını çözümleyin.
- Uyarıyı hata olarak değerlendirin.
- Kod hatası analizini geliştirmek için kaynak koda not ekleyin.

## <a name="prerequisites"></a>Önkoşullar

- [CppDemo örneğinin](../code-quality/demo-sample.md)bir kopyası.
- C/C++ hakkında temel bilgiler.

## <a name="run-code-analysis-on-native-code"></a>Yerel kodda Kod analizini Çalıştır

### <a name="to-run-code-defect-analysis-on-native-code"></a>Yerel kodda kod hatası analizini çalıştırmak için

::: moniker range=">=vs-2019"

1. Visual Studio 'da CppDemo çözümünü açın.

     CppDemo çözümü artık **Çözüm Gezgini**doldurur.

1. **Derle** menüsünde **çözümü yeniden derle**' yi seçin.

     Çözüm herhangi bir hata veya uyarı olmadan oluşturulur.

1. **Çözüm Gezgini**, codekusurları projesini seçin.

1. **Proje** menüsünde **Özellikler**' i seçin.

     **Codekusurları Özellik sayfaları** iletişim kutusu görüntülenir.

1. **Kod Analizi** özellik sayfasını seçin.

1. **Derleme üzerinde Kod analizini etkinleştir** özelliğini **Evet**olarak değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

1. Codekusurları projesini yeniden derleyin.

     Kod Analizi uyarıları **hata listesi** penceresinde görüntülenir.

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio 'da CppDemo çözümünü açın.

     CppDemo çözümü artık **Çözüm Gezgini**doldurur.

1. **Derle** menüsünde **çözümü yeniden derle**' yi seçin.

     Çözüm herhangi bir hata veya uyarı olmadan oluşturulur.

     > [!NOTE]
     > Visual Studio 2017 ' de, IntelliSense altyapısında bir çok değerli uyarı görebilirsiniz `E1097 unknown attribute "no_init_all"` . Bu uyarıyı güvenle yoksayabilirsiniz.

1. **Çözüm Gezgini**, codekusurları projesini seçin.

1. **Proje** menüsünde **Özellikler**' i seçin.

     **Codekusurları Özellik sayfaları** iletişim kutusu görüntülenir.

1. **Kod Analizi** özellik sayfasını seçin.

1. **Derlemede Kod analizini etkinleştir** onay kutusunu seçin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

1. Codekusurları projesini yeniden derleyin.

     Kod Analizi uyarıları **hata listesi** penceresinde görüntülenir.

::: moniker-end

### <a name="to-analyze-code-defect-warnings"></a>Kod hatası uyarılarını çözümlemek için

1. **Görünüm** menüsünde **hata listesi**' yi seçin.

     Bu menü öğesi görünür olmayabilir. Bu, Visual Studio 'da seçtiğiniz geliştirici profiline bağlıdır. **Görünüm** menüsünde **diğer pencereleri** işaret etmeniz ve ardından **hata listesi**seçmeniz gerekebilir.

1. **Hata listesi** penceresinde, aşağıdaki uyarıya çift tıklayın:

     C6230: anlamsal olarak farklı türler arasında örtük atama: Boole bağlamında HRESULT kullanılıyor.

     Kod Düzenleyicisi, işlevin içindeki uyarıya neden olan satırı görüntüler `bool ProcessDomain()` . Bu uyarı `HRESULT` , bir ' if ' bildiriminde bir Boole sonucunun beklendiğini gösterir. Genellikle bir hata olduğundan, `S_OK` HRESULT bir işlevden döndürüldüğünde başarılı olduğunu, ancak değerlendirilen bir Boole değerine dönüştürüldükten sonra **`false`** .

1. Bu uyarıyı `SUCCEEDED` , **`true`** bir `HRESULT` dönüş değeri başarıyı gösteriyorsa öğesine dönüştüren makrosunu kullanarak düzeltin. Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   if (SUCCEEDED(ReadUserAccount()))
   ```

1. **Hata listesi**, aşağıdaki uyarıya çift tıklayın:

     C6282: yanlış işleç: Boolean bağlamda sabit atama. Bunun yerine ' = = ' kullanmayı düşünün.

1. Bu uyarıyı, eşitlik için test ederek düzeltin. Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
   ```

1. ' İ başlatarak ve 0 ' a **hata listesi** kalan C6001 uyarılarını düzeltin `i` `j` .

1. Codekusurları projesini yeniden derleyin.

     Proje herhangi bir uyarı veya hata olmadan oluşturulur.

## <a name="correct-source-code-annotation-warnings"></a>Doğru kaynak kodu ek açıklaması uyarıları

### <a name="to-enable-the-source-code-annotation-warnings-in-annotationc"></a>Ek açıklamada kaynak kodu ek açıklaması uyarılarını etkinleştirmek için. c

::: moniker range=">=vs-2019"

1. Çözüm Gezgini, ek açıklamalar projesini seçin.

1. **Proje** menüsünde **Özellikler**' i seçin.

     **Ek açıklamalar Özellik sayfaları** iletişim kutusu görüntülenir.

1. **Kod Analizi** özellik sayfasını seçin.

1. **Derleme üzerinde Kod analizini etkinleştir** özelliğini **Evet**olarak değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

::: moniker-end

::: moniker range="<=vs-2017"

1. Çözüm Gezgini, ek açıklamalar projesini seçin.

1. **Proje** menüsünde **Özellikler**' i seçin.

     **Ek açıklamalar Özellik sayfaları** iletişim kutusu görüntülenir.

1. **Kod Analizi** özellik sayfasını seçin.

1. **Derlemede Kod analizini etkinleştir** onay kutusunu seçin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

::: moniker-end

### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>Ek açıklama. c ' de kaynak kodu ek açıklaması uyarılarını düzeltmek için

1. Ek açıklama projesini yeniden derleyin.

1. **Build** menüsünde, **ek açıklamalarda Kod analizini Çalıştır**' ı seçin.

1. **Hata listesi**, aşağıdaki uyarıya çift tıklayın:

     C6011: ' newNode ' NULL işaretçisinin başvurusunu kaldırma.

     Bu uyarı, çağıran tarafından döndürülen değeri denetlemek için hata olduğunu gösterir. Bu durumda, bir çağrısı `AllocateNode` null değeri döndürebilir. İçin işlev bildirimine yönelik ek açıklamalar. h üst bilgi dosyasına bakın `AllocateNode` .

1. İmleç, uyarının gerçekleştiği ek açıklamalar. cpp dosyasında yer alır.

1. Bu uyarıyı düzeltmek için, dönüş değerini test etmek için bir ' if ' ifadesini kullanın. Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   LinkedList* newNode = AllocateNode();
   if (nullptr != newNode)
   {
       newNode->data = value;
       newNode->next = 0;
       node->next = newNode;
   }
   ```

1. Ek açıklama projesini yeniden derleyin.

     Proje herhangi bir uyarı veya hata olmadan oluşturulur.

## <a name="use-source-code-annotation-to-discover-more-issues"></a>Diğer sorunları saptamak için kaynak kodu ek açıklamasını kullanın

### <a name="to-use-source-code-annotation"></a>Kaynak kodu ek açıklamasını kullanmak için

1. `AddTail`İşaretçi değerlerinin null olabileceğini göstermek için işlevin biçimsel parametrelere ve dönüş değerine açıklama ekleyin:

   ```cpp
   _Ret_maybenull_ LinkedList* AddTail(_Maybenull_ LinkedList* node, int value)
   ```

1. **Build** menüsünde, **çözüm üzerinde Kod analizini Çalıştır**' ı seçin.

1. **Hata listesi**, aşağıdaki uyarıya çift tıklayın:

     C6011: ' node ' NULL işaretçisine başvuruluyor.

     Bu uyarı, işleve geçirilen düğümün null olabileceğini gösterir.

1. Bu uyarıyı düzeltmek için, geçirilen değeri sınamak üzere işlevin başındaki bir ' if ' ifadesini kullanın. Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   if (nullptr == node)
   {
        return nullptr;
   }
   ```

1. **Build** menüsünde, **çözüm üzerinde Kod analizini Çalıştır**' ı seçin.

     Proje artık herhangi bir uyarı veya hata olmadan oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: kod kusurları için yönetilen kodu analiz etme](/visualstudio/code-quality/walkthrough-analyzing-managed-code-for-code-defects)\
[C/C++ için kod analizi](../code-quality/code-analysis-for-c-cpp-overview.md)
