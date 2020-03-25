---
title: 'Nasıl yapılır: derleme zamanında kaynakları dahil etme (C++)'
ms.date: 02/14/2019
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
- vc.editors.resourceincludes
helpviewer_keywords:
- comments [C++], compiled files
- resources [C++], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
- Resource Includes dialog box [C++]
- rc files [C++], changing storage
- symbol header files [C++], changing
- .rc files [C++], changing storage
- symbol header files [C++], read-only
- symbols [C++], symbol header files
- directories [C++], specifying include paths for resources
- include files [C++], specifying for resources
- resources [C++], including in projects
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: e931a0246340e81049df6ed0f8e26a4b91b570c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215205"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>Nasıl yapılır: derleme zamanında kaynakları dahil etme (C++)

Varsayılan olarak, tüm kaynaklar bir kaynak betiği (. RC) dosyasında bulunur, ancak kaynakları ana. rc dosyası dışında bir dosyaya yerleştirmek için birçok neden vardır:

- . Rc dosyasını kaydettiğinizde silinecek kaynak deyimlerine yorum eklemek için.

- Zaten geliştirilmiş ve test edilmiş ve daha fazla değişikliğe gerek olmayan kaynakları dahil etmek için. Dahil edilen ancak. RC uzantısı olmayan tüm dosyalar, kaynak düzenleyicileri tarafından düzenlenemez.

- Farklı projeler tarafından kullanılmakta olan veya kaynak kodu sürüm denetim sisteminin bir parçası olan kaynakları dahil etmek için. Bu kaynaklar, değişikliklerin tüm projeleri etkilediği merkezi bir konumda bulunmalıdır.

- Özel bir biçim olan kaynakları (örneğin, RCDATA kaynakları) dahil etmek için. RCDATA kaynakları, `nameID` alanı için değer olarak bir ifade kullanamıyoruz özel gereksinimlere sahiptir.

Mevcut. RC dosyalarınızda bu koşullardan herhangi birini karşılayan bölümleriniz varsa, bu bölümleri bir veya daha fazla ayrı. rc dosyasına yerleştirin ve **kaynak içerme** iletişim kutusunu kullanarak projenize ekleyin.

## <a name="resource-includes"></a>Kaynak eklemeleri

**Kaynak eklemeleri** Iletişim kutusunda **derleme zamanı yönergeleri** kutusunda bunları listeleyerek, derleme zamanında projenize başka dosyalardan kaynak ekleyebilirsiniz. Project. RC dosyasındaki tüm kaynakları ve `Resource.h`tüm [sembolleri](../windows/symbols-resource-identifiers.md) depolayan proje ortamının normal çalışma düzenini değiştirmek Için **kaynak içeriği** iletişim kutusunu kullanın.

Başlamak için [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)içinde bir. rc dosyasına sağ tıklayarak **kaynak içerme** Iletişim kutusunu açın, **kaynak içerme** ' yi seçin ve aşağıdaki özellikleri aklınızda edin:

| Özellik | Açıklama |
|---|---|
| **Sembol üst bilgi dosyası** | Kaynak dosyalarınızın sembol tanımlarının depolandığı üst bilgi dosyasının adını değiştirmenize izin verir.<br/><br/>Daha fazla bilgi için bkz. [sembol üstbilgi dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md). |
| **Salt okunurdur sembol yönergeleri** | Değiştirilmemelidir sembolleri içeren üst bilgi dosyalarını dahil etmenizi sağlar.<br/><br/>Örneğin, diğer projelerle paylaşılacak sembol dosyaları. Bu, MFC. h dosyalarını da içerebilir. Daha fazla bilgi için bkz. [Shared (salt okunurdur) veya hesaplanmış semboller ekleme](../windows/including-shared-read-only-or-calculated-symbols.md). |
| **Derleme zamanı yönergeleri** | Ana kaynak dosyanızdaki kaynaklardan ayrı olarak oluşturulan ve düzenlenen kaynak dosyalarını dahil etmenizi sağlar, derleme zamanı yönergeleri (kaynakları koşullu olarak dahil olan yönergeler gibi) veya özel bir biçimde kaynakları içerir.<br/><br/>Standart MFC kaynak dosyalarını dahil etmek için **derleme zamanı yönergeleri kutusunu** da kullanabilirsiniz. |

> [!NOTE]
> Bu metin kutularındaki girişler, sırasıyla `TEXTINCLUDE 1`, `TEXTINCLUDE 2`ve `TEXTINCLUDE 3` tarafından işaretlenmiş. rc dosyasında görünür. Daha fazla bilgi için bkz. [TN035: Visual C++Ile birden fazla kaynak dosyası ve üstbilgi dosyası kullanma ](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Kaynak dosya **eklemeleri** iletişim kutusu kullanılarak kaynak dosyanızda değişiklik yapıldıktan sonra değişikliklerin etkili olması için *. RC* dosyasını kapatıp yeniden açmanız gerekir.

### <a name="to-include-resources-in-your-project-at-compile-time"></a>Derleme zamanında projenize kaynak eklemek için

1. Kaynakları, benzersiz bir dosya adına sahip bir kaynak betik dosyasına yerleştirin. Asıl kaynak betik dosyası için kullanılan dosyanın adı olduğundan, *ProjectName. RC*kullanmayın.

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) *. RC* dosyasına sağ tıklayın ve **kaynak içerme**' yi seçin.

1. **Derleme zamanı yönergeleri** kutusunda, yeni kaynak dosyasını geliştirme ortamındaki ana kaynak dosyasına dahil etmek için [#include](../preprocessor/hash-include-directive-c-cpp.md) derleyici yönergesini ekleyin.

Bu şekilde, dosyalardaki kaynaklar yalnızca derleme sırasında yürütülebilir dosyanın bir parçası haline gelir ve projenin Main. rc dosyasında çalışırken düzenlenebilir veya değiştirilebilir. Dahil edilen. RC dosyalarının ayrı olarak açılması gerekir ve. RC uzantısı olmadan dahil edilen tüm dosyalar kaynak düzenleyicileri tarafından düzenlenemez.

### <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>Belirli bir kaynak (. RC) dosyası için içerme dizinlerini belirtmek için

1. **Çözüm Gezgini** içindeki *. RC* dosyasına sağ tıklayın ve **Özellikler**' i seçin.

1. Sol bölmedeki **kaynaklar** düğümünü seçin ve **ek içerme dizinleri** özelliğinde ek içerme dizinleri ' ni belirtin.

### <a name="to-find-symbols-in-resources"></a>Kaynaklardaki sembolleri bulmak için

1. Menü **düzenle** > [simge bul](/visualstudio/ide/go-to)' a gidin.

   > [!TIP]
   > Aramadaki [Normal ifadeleri](/visualstudio/ide/using-regular-expressions-in-visual-studio) kullanmak Için, **bul simgesi**yerine **Düzenle** menüsünde [dosyalarda bul](/visualstudio/ide/reference/find-command) ' u seçin. [Bul iletişim kutusunda](/visualstudio/ide/finding-and-replacing-text) **: normal ifadeler** **onay kutusunu seçin ve Aranan kutusunda,** açılan listeden bir normal arama ifadesi seçebilirsiniz. Bu listeden bir ifade seçtiğinizde, **Aranan kutusunda arama** metni olarak değiştirilir.

1. **Aranan kutusunda,** açılan listeden önceki bir arama dizesini seçin veya bulmak istediğiniz Hızlandırıcı anahtarını yazın, örneğin `ID_ACCEL1`.

1. **Bul** seçeneklerinden birini belirleyin ve **Sonrakini Bul**' u seçin.

> [!NOTE]
> Dize, Hızlandırıcı veya ikili kaynaklardaki sembolleri arayamaz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource-script-file.md)<br/>
[Nasıl yapılır: kaynakları yönetme](../windows/how-to-copy-resources.md)<br/>
