---
title: 'Nasıl yapılır: (C++) derleme sırasında kaynak ekleme'
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
ms.openlocfilehash: ca24a10f905e61feb2b090ba3966c752db3d4444
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041515"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>Nasıl yapılır: (C++) derleme sırasında kaynak ekleme

Varsayılan olarak, tüm kaynaklar bir kaynak betiği (.rc) dosyasında bulunur ancak ana .rc dosyasının farklı bir dosyadaki kaynakları yerleştirmek için birçok neden vardır:

- .Rc dosyasını kaydederken, silinir olmaz kaynak deyimleri için yorum eklemek için.

- Zaten geliştirdiğinizde ve test kaynakları içerecek şekilde ve daha fazla değişiklik gerekmez. Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.

- Farklı projeleri tarafından kullanıldığını ya da bir kaynak kod sürüm denetimi sisteminin bir parçası olan kaynakları dahil etmektir. Bu kaynaklar, tüm projeleri değişiklikler burada etkiler, merkezi bir konumda bulunmalıdır.

- Özel bir biçim kaynakları (örneğin, RCDATA kaynaklar) içerecek şekilde. RCDATA kaynaklara sahip olduğu kullanamazsınız bir ifade için bir değer olarak özel gereksinimler `nameID` alan.

Bölümler Bu koşullardan biri karşılaması, var olan bir .rc dosyası varsa, bu bölümler birinde yerleştirin veya daha fazla ayrı .rc dosyaları ve bunları kullanarak projenize dahil **kaynak içerikleri** iletişim kutusu.

## <a name="resource-includes"></a>Kaynak içerir

Kaynaklar diğer dosyaları projenize derleme zamanında bunları listeleyerek ekleyebilirsiniz **derleme zamanı yönergeleri** kutusunda **kaynak içerikleri** iletişim kutusu. Kullanım **kaynak içerikleri** proje ortamının tüm kaynaklar proje .rc dosyasını ve tüm depolama olarak normal çalışma düzenleme değiştirmek için iletişim kutusu [sembolleri](../windows/symbols-resource-identifiers.md) içinde `Resource.h`.

Başlamak için açık **kaynak içerikleri** bir .rc dosyasına sağ tıklayarak iletişim kutusunu [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)seçin **kaynak içerikleri** ve aşağıdaki özelliklere dikkat edin:

| Özellik | Açıklama |
|---|---|
| **Sembol başlık dosyası** | Kaynak dosyalar için Sembol tanımlarını depolandığı üst bilgi dosyasının adını değiştirmenizi sağlar.<br/><br/>Daha fazla bilgi için [sembol üst bilgi dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md). |
| **Salt okunur sembol yönergeleri** | Değiştirilmemelidir sembolleri içeren üstbilgi dosyalarını dahil etmenize imkan sağlar.<br/><br/>Örneğin, diğer projeleri ile paylaşılan dosyaları simge. Ayrıca, MFC .h dosyaları da ekleyebilirsiniz. Daha fazla bilgi için [dahil olmak üzere paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md). |
| **Derleme zamanı yönergeleri** | Oluşturulur ve ana kaynak dosyanızı kaynaklarda ayrı olarak düzenlenir kaynak dosyaları dahil etmenize olanak derleme zamanı yönergeleri (örneğin, kaynakları koşullu olarak dahil bu yönergeleri) içeren veya özel bir biçim kaynakları içerir.<br/><br/>Ayrıca **derleme zamanı yönergeleri kutusu** standart MFC kaynak dosyalarını dahil etmek için. |

> [!NOTE]
> Bu metin kutularındaki girişleri görünür olarak işaretlenmiş bir .rc dosyasında `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, ve `TEXTINCLUDE 3` sırasıyla. Daha fazla bilgi için [TN035: Visual C++ birden çok kaynak dosya ve üstbilgi dosyası kullanma](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Kullanarak, kaynak dosyaya değişiklikler yapıldıktan sonra **kaynak içerikleri** iletişim kutusunda, gereken kapatıp *.rc* değişikliklerin etkili olması dosya.

### <a name="to-include-resources-in-your-project-at-compile-time"></a>Kaynakları projenizde, derleme zamanında dahil etmek için

1. Benzersiz bir dosya adı ile kaynak betik dosyasını kaynakları yerleştirin. Kullanmayın *projectname.rc*, ana kaynak betik dosyası için kullanılan dosya adıdır.

1. Sağ *.rc* dosyası [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) seçip **kaynak içerikleri**.

1. İçinde **derleme zamanı yönergeleri** kutusunda [#include](../preprocessor/hash-include-directive-c-cpp.md) ana kaynak dosyasıyla geliştirme ortamındaki yeni kaynak dosyası eklemek için derleyici yönergesi.

Bu şekilde dahil dosyalarındaki kaynaklar bölümü yürütülebilir dosyanın derleme zamanında yalnızca yapılır ve projenizin ana .rc dosyası üzerinde çalışırken, düzenleme veya değiştirilmesi için kullanılamaz. Dahil edilen bir .rc dosyası ayrı olarak açılması gerekir ve .rc uzantısı olmadan dahil tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.

### <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>Belirtmek için belirli bir kaynak (.rc) dosyası için dizinleri dahil et

1. Sağ *.rc* dosyası **Çözüm Gezgini** seçip **özellikleri**.

1. Seçin **kaynakları** sol bölmedeki düğüm ve ek dizinleri dahil **ek dizinleri** özelliği.

### <a name="to-find-symbols-in-resources"></a>Semboller kaynakları bulmak için

1. Menü Git **Düzenle** > [sembol Bul'u](/visualstudio/ide/go-to).

   > [!TIP]
   > Kullanılacak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) aramanızda seçin [dosyalarda Bul](/visualstudio/ide/reference/find-command) içinde **Düzenle** menü yerine **sembol Bul'u**. Seçin **kullanın: Normal ifadeler** onay kutusuna [Bul iletişim kutusu](/visualstudio/ide/finding-and-replacing-text) ve **Aranan** kutusunda aşağı açılan listeden bir arama normal ifade seçebilirsiniz. Bu listeden bir ifade seçtiğinizde, arama metni olarak geçmesidir **Aranan** kutusu.

1. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz, örneğin, Hızlandırıcı anahtar türü `ID_ACCEL1`.

1. Herhangi bir **Bul** seçenekleri ve seçin **Sonrakini Bul**.

> [!NOTE]
> Dize, Hızlandırıcı veya ikili kaynaklar sembolleri arama yapamazsınız.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: Kaynak oluştur](../windows/how-to-create-a-resource-script-file.md)<br/>
[Nasıl yapılır: Kaynakları yönet](../windows/how-to-copy-resources.md)<br/>