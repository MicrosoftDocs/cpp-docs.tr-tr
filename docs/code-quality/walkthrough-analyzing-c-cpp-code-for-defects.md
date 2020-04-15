---
title: 'İzleyici: Hatalar için C/C++ kodunu çözümleme'
description: Visual Studio'da Microsoft C++ ile kod çözümlemesi nasıl kullanılacağını gösterir.
ms.date: 04/14/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.openlocfilehash: fe9b3775199b2a18cf940b99e87852350f1fbea9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370212"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>İzleyici: Hatalar için C/C++ kodunu çözümleme

Bu izbis, olası kod hataları için C/C++ kodunun nasıl analiz edilebildiğini gösterir. C/C++ kodu için kod çözümleme araçlarını kullanır.

Bu izne göre:

- Yerel kodüzerinde kod çözümlemesi çalıştırın.
- Kod hatası uyarılarını analiz edin.
- Uyarıyı bir hata olarak ele a.r.'a.
- Kod defekti çözümlemesi geliştirmek için kaynak koduna açıklama yapın.

## <a name="prerequisites"></a>Ön koşullar

- [CppDemo Örneğinin](../code-quality/demo-sample.md)bir kopyası.
- C/C++'ın temel anlayışı.

## <a name="run-code-analysis-on-native-code"></a>Yerel kodda kod çözümlemesi çalıştırma

### <a name="to-run-code-defect-analysis-on-native-code"></a>Yerel kodda kod defekti çözümlemesi çalıştırmak için

::: moniker range=">=vs-2019"

1. Visual Studio'da CppDemo çözümlerini açın.

     CppDemo çözümü artık **Çözüm Gezgini'ni**dolduruyor.

1. **Yapı** menüsünde **Çözümü Yeniden Oluştur'u**seçin.

     Çözüm herhangi bir hata veya uyarı olmadan oluşturur.

1. **Çözüm Gezgini'nde**CodeDefects projesini seçin.

1. **Proje** menüsünde **Özellikler'i**seçin.

     **CodeDefects Özellik Sayfaları** iletişim kutusu görüntülenir.

1. Kod **Analizi** özellik sayfasını seçin.

1. Yapı **özelliğinde Kod Çözümlemesini Etkinleştir'i** **Evet**olarak değiştirin. Değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

1. CodeDefects projesini yeniden oluştur.

     Kod çözümleme uyarıları **Hata Listesi** penceresinde görüntülenir.

::: moniker-end

::: moniker range="<=vs-2017"

1. Visual Studio'da CppDemo çözümlerini açın.

     CppDemo çözümü artık **Çözüm Gezgini'ni**dolduruyor.

1. **Yapı** menüsünde **Çözümü Yeniden Oluştur'u**seçin.

     Çözüm herhangi bir hata veya uyarı olmadan oluşturur.

     > [!NOTE]
     > Visual Studio 2017'de IntelliSense `E1097 unknown attribute "no_init_all"` motorunda sahte bir uyarı görebilirsiniz. Bu uyarıyı güvenle yoksayabilirsiniz.

1. **Çözüm Gezgini'nde**CodeDefects projesini seçin.

1. **Proje** menüsünde **Özellikler'i**seçin.

     **CodeDefects Özellik Sayfaları** iletişim kutusu görüntülenir.

1. Kod **Analizi** özellik sayfasını seçin.

1. Yapı onay kutusunda **Kod Çözümlemesini Etkinleştir'i** seçin. Değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

1. CodeDefects projesini yeniden oluştur.

     Kod çözümleme uyarıları **Hata Listesi** penceresinde görüntülenir.

::: moniker-end

### <a name="to-analyze-code-defect-warnings"></a>Kod hatası uyarılarını analiz etmek için

1. **Görünüm** menüsünde **Hata Listesi'ni**seçin.

     Bu menü öğesi görünmeyebilir. Visual Studio'da seçtiğiniz geliştirici profiline bağlıdır. **Görünüm** menüsündeki **Diğer Windows'u** işaret edip ardından **Hata Listesi'ni**seçmeniz gerekebilir.

1. Hata **Listesi** penceresinde, aşağıdaki uyarıyı çift tıklatın:

     C6230: Anlamsal olarak farklı türler arasında örtük döküm: Boolean bağlamında HRESULT kullanarak.

     Kod düzenleyicisi, işlevin `bool ProcessDomain()`içindeki uyarıya neden olan satırı görüntüler. Bu uyarı, `HRESULT` Boolean sonucunun beklendiği 'if' deyiminde a'nın kullanıldığını gösterir. Bu genellikle bir hatadır, çünkü `S_OK` HRESULT bir işlevden döndürüldüğünde başarıyı gösterir, ancak boolean değerine dönüştürüldüğünde bunu `false`değerlendirir.

1. Bu uyarıyı, `SUCCEEDED` geri dönüş değeri `true` başarıyı gösterdiğinde dönüştüren makroyu kullanarak düzeltin. `HRESULT` Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   if (SUCCEEDED(ReadUserAccount()))
   ```

1. Hata **Listesinde,** aşağıdaki uyarıyı çift tıklatın:

     C6282: Yanlış işleç: Boolean bağlamında sabit atama. Bunun yerine '==' kullanmayı düşünün.

1. Eşitlik için test ederek bu uyarıyı düzeltin. Kodunuz aşağıdaki koda benzer olmalıdır:

   ```cpp
   if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
   ```

1. **Hata Listesinde** kalan C6001 uyarılarını baş `i` `j` harfe ve 0'a doğru düzeltin.

1. CodeDefects projesini yeniden oluştur.

     Proje herhangi bir uyarı veya hata olmadan oluşturur.

## <a name="correct-source-code-annotation-warnings"></a>Kaynak kodu ek açıklama uyarılarını düzeltin

### <a name="to-enable-the-source-code-annotation-warnings-in-annotationc"></a>Ek açıklama.c'deki kaynak kodu ek açıklama uyarılarını etkinleştirmek için

::: moniker range=">=vs-2019"

1. Çözüm Gezgini'nde Ek Açıklamalar projesini seçin.

1. **Proje** menüsünde **Özellikler'i**seçin.

     **Ek Açıklamalar Özellik Sayfaları** iletişim kutusu görüntülenir.

1. Kod **Analizi** özellik sayfasını seçin.

1. Yapı **özelliğinde Kod Çözümlemesini Etkinleştir'i** **Evet**olarak değiştirin. Değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

::: moniker-end

::: moniker range="<=vs-2017"

1. Çözüm Gezgini'nde Ek Açıklamalar projesini seçin.

1. **Proje** menüsünde **Özellikler'i**seçin.

     **Ek Açıklamalar Özellik Sayfaları** iletişim kutusu görüntülenir.

1. Kod **Analizi** özellik sayfasını seçin.

1. Yapı onay kutusunda **Kod Çözümlemesini Etkinleştir'i** seçin. Değişikliklerinizi kaydetmek için **Tamam'ı** seçin.

::: moniker-end

### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>Ek açıklama.c'deki kaynak kodu ek açıklama uyarılarını düzeltmek için

1. Ek Açıklamalar projesini yeniden oluştur.

1. **Yapı** menüsünde, **Ek Açıklamalar üzerinde Kod Çözümlemesi'ni**seçin.

1. Hata **Listesinde,** aşağıdaki uyarıyı çift tıklatın:

     C6011: NULL işaretçisi 'newNode' dereferencing.

     Bu uyarı, arayanın iade değerini denetlemedeki başarısızlığını gösterir. Bu durumda, bir `AllocateNode` çağrı NULL değeri döndürebilir. İşlev bildirimi için ek açıklamalar.h üstbilgi `AllocateNode`dosyasına bakın.

1. İmleç, uyarının oluştuğu ek açıklamalar.cpp dosyasındaki konumdadır.

1. Bu uyarıyı düzeltmek için, iade değerini sınamak için 'if' deyimini kullanın. Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   LinkedList* newNode = AllocateNode();
   if (nullptr != newNode)
   {
       newNode->data = value;
       newNode->next = 0;
       node->next = newNode;
   }
   ```

1. Ek Açıklamalar projesini yeniden oluştur.

     Proje herhangi bir uyarı veya hata olmadan oluşturur.

## <a name="use-source-code-annotation-to-discover-more-issues"></a>Daha fazla sorunu keşfetmek için kaynak kodu ek açıklamasını kullanma

### <a name="to-use-source-code-annotation"></a>Kaynak kodu ek açıklamasını kullanmak için

1. İşaretçi değerlerinin null olabileceğini belirtmek `AddTail` için resmi parametrelere ve işlevin return value'a açıklama ekedin:

   ```cpp
   _Ret_maybenull_ LinkedList* AddTail(_Maybenull_ LinkedList* node, int value)
   ```

1. **Yapı** menüsünde, **Çözümde Kod Çözümle'yi Çalıştır'ı**seçin.

1. Hata **Listesinde,** aşağıdaki uyarıyı çift tıklatın:

     C6011: NULL işaretçisi 'düğüm' dereferencing.

     Bu uyarı, işleve geçen düğümün null olabileceğini gösterir.

1. Bu uyarıyı düzeltmek için, geçen değeri sınamak için işlevin başında bir 'if' deyimi kullanın. Kodunuz aşağıdaki koda benzemelidir:

   ```cpp
   if (nullptr == node)
   {
        return nullptr;
   }
   ```

1. **Yapı** menüsünde, **Çözümde Kod Çözümle'yi Çalıştır'ı**seçin.

     Proje artık herhangi bir uyarı veya hata olmadan oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenme: Kod Hataları için Yönetilen Kodu Çözümleme](/visualstudio/code-quality/walkthrough-analyzing-managed-code-for-code-defects)\
[C/C++ için kod analizi](../code-quality/code-analysis-for-c-cpp-overview.md)
