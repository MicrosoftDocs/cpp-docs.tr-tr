---
description: 'Daha fazla bilgi edinin: Ikili Düzenleyici (C++)'
title: İkili Düzenleyici (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.binary.F1
- vc.editors.binary
helpviewer_keywords:
- editors, Binary
- resources [C++], editing
- resource editors [C++], Binary editor
- Binary editor
- binary data, editing
- resources [C++], opening for binary editing
- binary data
- hexadecimal bytes in binary data
- strings [C++], searching for
- file searches [C++]
- binary data, finding
- ASCII characters, finding in binary data
- custom resources [C++]
- data resources [C++]
- resources [C++], creating
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
ms.openlocfilehash: 8abe63f662d25b5e8108d0671dd17490143a07fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327219"
---
# <a name="binary-editor-c"></a>İkili Düzenleyici (C++)

> [!CAUTION]
> **Ikili düzenleyicideki** iletişim kutuları, görüntüler veya menüler gibi kaynakları düzenleme tehlikeli olur. Hatalı düzenleme, kaynağı bozmadan yerel düzenleyicide okunamaz hale getirir.

**Ikili düzenleyici** , herhangi bir kaynağı, ONALTıLı veya ASCII biçiminde ikili düzeyde düzenlemenizi sağlar. [Find komutunu](/visualstudio/ide/reference/find-command) , ASCII dizelerini veya onaltılı baytları aramak için de kullanabilirsiniz. **Ikili düzenleyiciyi** yalnızca, Visual Studio ortamı tarafından desteklenmeyen özel kaynaklarda veya kaynak türlerinde küçük değişiklikler yapmanız veya bunları görüntülemeniz gerektiğinde kullanın. **Ikili düzenleyici** Express sürümlerinde kullanılamaz.

- **İkili düzenleyiciyi** yeni bir dosya üzerinde açmak için, menü **dosyası**  >  **Yeni**  >  **Dosya**' ya gidin, düzenlemek istediğiniz dosya türünü seçin, sonra **Aç** düğmesinin yanındaki açılan oku seçin ve   >  **ikili düzenleyiciyle** aç ' ı seçin.

- **İkili düzenleyiciyi** mevcut bir dosyada açmak için, menü **dosyası**  >    >  **Dosya** aç ' a gidin, düzenlemek istediğiniz dosyayı seçin, sonra **Aç** düğmesinin yanındaki açılan oku seçin ve   >  **ikili düzenleyiciyle** aç ' ı seçin.

   ![İkili Düzenleyici](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
   **Ikili düzenleyicide** gösterildiği bir iletişim kutusu için ikili veriler

**Ikili düzenleyicide** yalnızca belirli ASCII değerleri temsil edilir (0x20 ile 0x7E). Genişletilmiş karakterler, **Ikili düzenleyicinin** sağ panel ASCII değeri bölümünde nokta olarak görüntülenir. Yazdırılabilir karakterler 32 ile 126 arasında ASCII değerlerdir.

> [!TIP]
> **Ikili düzenleyiciyi** kullanırken, birçok örnekte kaynağa özgü komutların kısayol menüsünü göstermek için sağ tıklayabilirsiniz. Kullanılabilir komutlar, imlecinizin ne olduğuna bağlıdır. Örneğin, seçili onaltılık değerlerle **Ikili düzenleyiciyi** işaret ederken sağ tıkladığınızda, kısayol menüsü **Kes**, **Kopyala** ve **Yapıştır** komutlarını gösterir.

## <a name="how-to"></a>Nasıl yapılır

**Ikili düzenleyici** şunları yapmanızı mümkün:

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>İkili dosya düzenlemesi için bir Windows Masaüstü kaynağını açmak için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), düzenlemek istediğiniz belirli kaynak dosyasını seçin.

1. Kaynağa sağ tıklayın ve **Ikili verileri aç**' ı seçin.

> [!NOTE]
> Bir kaynağı, RCDATA veya özel bir kaynak gibi Visual Studio 'Nun tanımadığı bir biçimde açmak için **kaynak görünümü** penceresini kullanırsanız, kaynak **ikili düzenleyicide** otomatik olarak açılır.

### <a name="to-open-a-managed-resource-for-binary-editing"></a>Bir yönetilen kaynağı ikili düzenlemeyle açmak için

1. **Çözüm Gezgini**, düzenlemek istediğiniz belirli kaynak dosyasını seçin.

1. Kaynağa sağ tıklayın ve **birlikte Aç**' ı seçin.

1. **Birlikte Aç** Iletişim kutusunda **ikili düzenleyici**' yi seçin.

> [!NOTE]
> Yönetilen projelerde kaynak dosyalarıyla çalışmak için [resim düzenleyicisini](image-editor-for-icons.md) ve **ikili düzenleyiciyi** kullanabilirsiniz. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

### <a name="to-edit-a-resource"></a>Bir kaynağı düzenlemek için

Zaten başka bir düzenleyici penceresinde düzenlenmekte olan bir kaynakta **Ikili düzenleyiciyi** kullanmak istiyorsanız, önce diğer düzenleyici penceresini kapatın.

1. Düzenlemek istediğiniz baytı seçin.

   **Tab** tuşu, odağı **ikili DÜZENLEYICININ** onaltılı ve ASCII bölümleri arasında taşınır. Tek seferde bir ekran arasında ilerlemek için, **sayfa yukarı** ve **sayfa aşağı** tuşlarını kullanabilirsiniz.

1. Yeni değeri yazın.

   Değer hem onaltılık hem de ASCII bölümlerinde hemen değişir ve odak satırdaki sonraki değere kayar.

> [!NOTE]
> Düzenleyiciyi kapattığınızda **Ikili düzenleyici** değişiklikleri otomatik olarak kabul eder.

### <a name="to-find-binary-data"></a>İkili verileri bulmak için

ASCII dizeleri veya onaltılı baytlar için arama yapabilirsiniz. Örneğin, *Hello*'yu bulmak Için, *Hello* dize veya on altılı değeri olan *48 65 6c 6c 6F* için arama yapabilirsiniz.

1. Menü **Düzenle**  >  [bul](/visualstudio/ide/reference/find-command)' a gidin.

1. **Aranan kutusunda,** açılan listeden önceki bir arama dizesini seçin veya bulmak istediğiniz verileri yazın.

1. **Bul** seçeneklerinden birini belirleyin ve **Sonrakini Bul**' u seçin.

### <a name="to-create-a-new-custom-or-data-resource"></a>Yeni bir özel veya veri kaynağı oluşturmak için

Kaynağı normal kaynak betiği (. RC) dosya söz dizimini kullanarak ayrı bir dosyaya yerleştirerek ve sonra **Çözüm Gezgini** ve **kaynak içermeler**' i seçerek bu dosyayı içeren yeni bir özel veya veri kaynağı oluşturabilirsiniz.

1. Özel veya veri kaynağını içeren [bir. rc dosyası oluşturun](how-to-create-a-resource-script-file.md) .

   Bir. rc dosyasında, null ile sonlandırılmış alıntılanmış dizeler veya ondalık, onaltılık veya sekizlik biçimde tamsayı olarak özel veri yazabilirsiniz.

1. **Çözüm Gezgini**, projenizin. rc dosyasına sağ tıklayın ve **kaynak içermeler**' i seçin.

1. **Derleme zamanı yönergeleri** kutusuna `#include` özel kaynağınızı içeren dosyanın adını veren bir ifade yazın, örneğin:

    ```cpp
    #include mydata.rc
    ```

   Yazımın sözdiziminin ve yazımın doğru olduğundan emin olun. **Derleme zamanı yönergeleri** kutusunun içeriği, tam olarak siz yazarken kaynak betik dosyasına eklenir.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

Özel bir kaynak oluşturmanın başka bir yolu da bir dış dosyayı özel kaynak olarak içeri aktarmanız, bkz. [nasıl yapılır: kaynakları yönetme](./how-to-copy-resources.md).

> [!NOTE]
> Yeni özel veya veri kaynakları oluşturmak Win32 gerektirir.

## <a name="requirements"></a>Gereksinimler

Yok

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak düzenleyicileri](resource-editors.md)
