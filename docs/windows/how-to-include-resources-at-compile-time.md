---
title: 'Nasıl yapılır: (C++) derleme sırasında kaynak ekleme'
ms.date: 11/04/2016
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
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
ms.openlocfilehash: 52145d2a656a7cac0d07a43ceaf298fbebb5ad40
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55764083"
---
# <a name="how-to-include-resources-at-compile-time"></a>Nasıl yapılır: Derleme sırasında kaynak ekleme

Normalde tüm kaynaklar bir kaynak betiği (.rc) dosyasında varsayılan düzenini çalışmak daha kolay olur. Ancak, kaynaklar diğer dosyalar geçerli projenizi derleme zamanında bunları listeleyerek ekleyebilirsiniz **derleme zamanı yönergeleri** kutusunda **kaynak içerikleri** iletişim kutusu.

Ana .rc dosyasının farklı bir dosyadaki kaynakları yerleştirmek için birkaç nedeni vardır:

- .Rc dosyasını kaydederken, silinir olmaz kaynak deyimleri için yorum eklemek için.

   Kaynak düzenleyicileri doğrudan .rc okuma yok veya `resource.h` dosyaları. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik olmayan bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasının üzerine yazar ve `resource.h` dosyası). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak.

- Zaten geliştirdiğinizde ve test kaynakları içerecek şekilde ve daha fazla değişiklik gerekmez. (Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.)

- Birkaç farklı proje tarafından kullanılmakta olan veya, bir kaynak kod sürüm denetimi sisteminin bir parçası olan ve bu nedenle değişiklikleri tüm projeleri burada etkiler, merkezi bir konumda mevcut olmalıdır kaynakları dahil etmektir.

- Özel bir biçimde kaynakları (örneğin, RCDATA kaynaklar) içerecek şekilde. RCDATA kaynaklar özel gereksinimlerine sahip olabilir. Örneğin, bir ifade Nameıd alan için bir değer olarak kullanamazsınız. Daha fazla bilgi için Windows SDK belgelerine bakın.

Bölümler Bu koşullardan biri karşılaması, var olan bir .rc dosyası varsa, biri bölümlerde yerleştirmeniz gerekir veya daha fazla ayrı .rc dosyaları ve bunları kullanarak projenize dahil **kaynak içerikleri** iletişim kutusu. *Projectname*.rc2 dosya yeni bir proje \res alt dizinde oluşturulur, bu amaçla kullanılır.

Kullanabileceğiniz **kaynak içerikleri** ortamının tüm kaynaklar proje .rc dosyasını ve tüm depolama olarak normal çalışma düzenleme değiştirmek için bir C++ projesi iletişim kutusunda [sembolleri](../windows/symbols-resource-identifiers.md) Resource.h içindeki.

Açmak için **kaynak içerikleri** iletişim kutusunda sağ tıklatıp bir .rc dosyasına [kaynak görünümü](../windows/resource-view-window.md), ardından **kaynak içerikleri** kısayol menüsünden. Bu iletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Sembol başlık dosyası**|Kaynak dosyanız için Sembol tanımlarını depolandığı üst bilgi dosyasının adını değiştirmenizi sağlar. Daha fazla bilgi için [sembol üst bilgi dosyalarının adlarını değiştirme](../windows/changing-the-names-of-symbol-header-files.md).|
|**Salt okunur sembol yönergeleri**|Bir düzenleme oturumu sırasında değiştirilmemelidir sembolleri içeren üstbilgi dosyalarını dahil etmenize imkan sağlar. Örneğin, çeşitli projeler arasında paylaşılan bir sembol dosyası içerebilir. MFC .h dosyaları da ekleyebilirsiniz. Daha fazla bilgi için [dahil olmak üzere paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).|
|**Derleme zamanı yönergeleri**|Oluşturulur ve ana kaynak dosyanızı kaynaklarda ayrı olarak düzenlenir kaynak dosyaları dahil etmenize olanak derleme zamanı yönergeleri (örneğin, kaynakları koşullu olarak dahil bu yönergeleri) içeren veya özel bir biçim kaynakları içerir. Ayrıca **derleme zamanı yönergeleri kutusu** standart MFC kaynak dosyalarını dahil etmek için. Daha fazla bilgi için [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).|

> [!NOTE]
> Bu metin kutularındaki girişleri görünür olarak işaretlenmiş bir .rc dosyasında `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, ve `TEXTINCLUDE 3` sırasıyla. Daha fazla bilgi için [TN035: Visual C++ birden çok kaynak dosya ve üstbilgi dosyası kullanma](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Kullanarak, kaynak dosyaya değişiklikleri yaptıktan sonra **kaynak içerikleri** iletişim kutusunda, gereken .rc dosyasını kapatın ve değişikliklerin etkili olması yeniden açın. Daha fazla bilgi için [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) .NET Framework Geliştirici Kılavuzu'nda.

## <a name="to-include-resources-in-your-project-at-compile-time"></a>Kaynakları projenizde, derleme zamanında dahil etmek için

1. Benzersiz bir dosya adı ile kaynak betik dosyasını kaynakları yerleştirin. Kullanmayın *projectname*.rc, çünkü bu adı ana kaynak betik dosyası için kullanılan dosya adı.

1. .Rc dosyasına sağ tıklayın (içinde [kaynak görünümü](../windows/resource-view-window.md)) seçip **kaynak içerikleri** kısayol menüsünden.

1. İçinde **derleme zamanı yönergeleri** kutusunda [#include](../preprocessor/hash-include-directive-c-cpp.md) ana kaynak dosyasıyla geliştirme ortamındaki yeni kaynak dosyası eklemek için derleyici yönergesi.

   Bu şekilde dahil dosyalarındaki kaynaklar, yürütülebilir dosya, derleme zamanında yapılır. Projenizin ana .rc dosyası üzerinde çalışırken, düzenlemek veya değişiklik için doğrudan kullanılabilir değildir. Dahil edilen bir .rc dosyası ayrı olarak açın. Dahil edilir, ancak bir .rc uzantısı yoksa tüm dosyaları kaynak düzenleyicileri tarafından düzenlenebilir olmayacaktır.

## <a name="to-specify-include-directories-for-a-specific-resource-rc-file-c"></a>Belirtmek için ekleme kodu dizinleri belirli bir kaynaktan (.rc dosyası) (C++)

1. Çözüm Gezgini'nde .rc dosyasına sağ tıklayıp **özellikleri** kısayol menüsünden.

1. İçinde **özellik sayfaları** iletişim kutusunda **kaynakları** düğümü sol bölmede, ardından belirtin ek içeren dizinler **ek ekleme dizinleri**özelliği.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[TN035: Visual C++ birden çok kaynak dosya ve üstbilgi dosyası kullanma](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)<br/>
[Semboller: Kaynak Tanımlayıcıları](../windows/symbols-resource-identifiers.md)<br/>
