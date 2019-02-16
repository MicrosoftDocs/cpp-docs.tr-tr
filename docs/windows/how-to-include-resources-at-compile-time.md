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
ms.openlocfilehash: 06ad2f90e7e72492f1e6ca4000a6c101fc36b205
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320672"
---
# <a name="how-to-include-resources-at-compile-time-c"></a>Nasıl yapılır: (C++) derleme sırasında kaynak ekleme

Normalde tüm kaynaklar bir kaynak betiği (.rc) dosyasında varsayılan düzenini çalışmak daha kolay olur. Ancak, ana .rc dosyasının farklı bir dosyadaki kaynakları yerleştirmek için birkaç nedeni vardır:

- .Rc dosyasını kaydederken, silinir olmaz kaynak deyimleri için yorum eklemek için.

   Kaynak düzenleyicileri doğrudan .rc okuma yok veya `resource.h` dosyaları. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik olmayan bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasının üzerine yazar ve `resource.h` dosyası). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak.

- Zaten geliştirdiğinizde ve test kaynakları içerecek şekilde ve daha fazla değişiklik gerekmez. (Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.)

- Birkaç farklı proje tarafından kullanılmakta olan veya, bir kaynak kod sürüm denetimi sisteminin bir parçası olan ve bu nedenle değişiklikleri tüm projeleri burada etkiler, merkezi bir konumda mevcut olmalıdır kaynakları dahil etmektir.

- Özel bir biçimde kaynakları (örneğin, RCDATA kaynaklar) içerecek şekilde. RCDATA kaynaklar özel gereksinimlerine sahip olabilir. Örneğin, bir ifade Nameıd alan için bir değer olarak kullanamazsınız. Daha fazla bilgi için Windows SDK belgelerine bakın.

## <a name="resource-includes"></a>Kaynak içerir

Kaynaklar diğer dosyalar için geçerli projeyi derleme zamanında bunları listeleyerek ekleyebilirsiniz **derleme zamanı yönergeleri** kutusunda **kaynak içerikleri** iletişim kutusu.

Bölümler Bu koşullardan biri karşılaması, var olan bir .rc dosyası varsa, biri bölümlerde yerleştirmeniz gerekir veya daha fazla ayrı .rc dosyaları ve bunları kullanarak projenize dahil **kaynak içerikleri** iletişim kutusu. *Projectname*.rc2 dosya yeni bir proje \res alt dizinde oluşturulur, bu amaçla kullanılır.

Kullanabileceğiniz **kaynak içerikleri** ortamının tüm kaynaklar proje .rc dosyasını ve tüm depolama olarak normal çalışma düzenleme değiştirmek için bir C++ projesi iletişim kutusunda [sembolleri](../windows/symbols-resource-identifiers.md) Resource.h içindeki.

Açmak için **kaynak içerikleri** iletişim kutusunda sağ tıklatıp bir .rc dosyasına [kaynak görünümü](../windows/resource-view-window.md), ardından **kaynak içerikleri** kısayol menüsünden. Aşağıdaki özelliklere bakın:

|Özellik|Açıklama|
|--|----|
|**Sembol başlık dosyası**|Kaynak dosyanız için Sembol tanımlarını depolandığı üst bilgi dosyasının adını değiştirmenizi sağlar. Daha fazla bilgi için [sembol üst bilgi dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md).|
|**Salt okunur sembol yönergeleri**|Bir düzenleme oturumu sırasında değiştirilmemelidir sembolleri içeren üstbilgi dosyalarını dahil etmenize imkan sağlar. Örneğin, çeşitli projeler arasında paylaşılan bir sembol dosyası içerebilir. MFC .h dosyaları da ekleyebilirsiniz. Daha fazla bilgi için [dahil olmak üzere paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).|
|**Derleme zamanı yönergeleri**|Oluşturulur ve ana kaynak dosyanızı kaynaklarda ayrı olarak düzenlenir kaynak dosyaları dahil etmenize olanak derleme zamanı yönergeleri (örneğin, kaynakları koşullu olarak dahil bu yönergeleri) içeren veya özel bir biçim kaynakları içerir. Ayrıca **derleme zamanı yönergeleri kutusu** standart MFC kaynak dosyalarını dahil etmek için.|

> [!NOTE]
> Bu metin kutularındaki girişleri görünür olarak işaretlenmiş bir .rc dosyasında `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, ve `TEXTINCLUDE 3` sırasıyla. Daha fazla bilgi için [TN035: Visual C++ birden çok kaynak dosya ve üstbilgi dosyası kullanma](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Kullanarak, kaynak dosyaya değişiklikleri yaptıktan sonra **kaynak içerikleri** iletişim kutusunda, gereken .rc dosyasını kapatın ve değişikliklerin etkili olması yeniden açın.

### <a name="to-include-resources-in-your-project-at-compile-time"></a>Kaynakları projenizde, derleme zamanında dahil etmek için

1. Benzersiz bir dosya adı ile kaynak betik dosyasını kaynakları yerleştirin. Kullanmayın *projectname*.rc, çünkü bu adı ana kaynak betik dosyası için kullanılan dosya adı.

1. .Rc dosyasına sağ tıklayın (içinde [kaynak görünümü](../windows/resource-view-window.md)) seçip **kaynak içerikleri** kısayol menüsünden.

1. İçinde **derleme zamanı yönergeleri** kutusunda [#include](../preprocessor/hash-include-directive-c-cpp.md) ana kaynak dosyasıyla geliştirme ortamındaki yeni kaynak dosyası eklemek için derleyici yönergesi.

   Bu şekilde dahil dosyalarındaki kaynaklar, yürütülebilir dosya, derleme zamanında yapılır. Projenizin ana .rc dosyası üzerinde çalışırken, düzenlemek veya değişiklik için doğrudan kullanılabilir değildir. Dahil edilen bir .rc dosyası ayrı olarak açın. Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.

### <a name="to-specify-include-directories-for-a-specific-resource-rc-file"></a>Belirtmek için belirli bir kaynak (.rc dosyası) için dizinleri dahil et

1. Çözüm Gezgini'nde .rc dosyasına sağ tıklayıp **özellikleri** kısayol menüsünden.

1. Seçin **kaynakları** sol bölmedeki düğüm ve ek dizinleri dahil **ek dizinleri** özelliği.

### <a name="to-find-symbols-in-resources"></a>Semboller kaynakları bulmak için

1. Gelen **Düzenle** menüsünde seçin [sembol Bul'u](/visualstudio/ide/go-to).

1. İçinde **Aranan** kutusunda aşağı açılan listeden önceki bir arama dizesi seçin veya bulmak istediğiniz kısayol tuşu yazın (örneğin, `ID_ACCEL1`).

   > [!TIP]
   > Kullanılacak [normal ifadeler](/visualstudio/ide/using-regular-expressions-in-visual-studio) aramanız için kullanmalısınız [dosyalarda Bul komutu](/visualstudio/ide/reference/find-command) gelen **Düzenle** menü yerine **sembol Bul'u**komutu. Normal ifadeler etkinleştirmek için olmalıdır **kullanın: Normal ifadeler** onay kutusunu seçili [Bul iletişim kutusu](/visualstudio/ide/finding-and-replacing-text). Sağ ok düğmesine sağındaki seçip **Aranan** normal arama listesini görüntülemek için kutusu. Bu listeden bir ifade seçtiğinizde, arama metni olarak geçmesidir **Aranan** kutusu.

1. Herhangi bir **Bul** seçenekleri ve seçin **Sonrakini Bul**.

> [!NOTE]
> Dize, Hızlandırıcı veya ikili kaynaklar sembolleri arama yapamazsınız.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynakları oluşturma](../windows/how-to-create-a-resource-script-file.md)<br/>
[Kaynakları yönetme](../windows/how-to-copy-resources.md)<br/>