---
title: Kaynak Dosyalar (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- resources [C++]
- .rc files [C++]
- resource files [C++]
- resource script files [C++]
- resource script files [C++], Win-32 based applications
- resource script files [C++], files updated when editing resources
- resources [C++], types of resource files
- rct files [C++]
- rc files [C++]
- resource files [C++], types of
- .rct files [C++]
- resource script files [C++], unsupported types
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
- file types [C++], for resources
- resources [C++], editing
- files [C++], editable types
- resource editing
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
ms.openlocfilehash: 45db6d0139cfa3aa8a2eaa8fe6d18158cb6646ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387922"
---
# <a name="resource-files-c"></a>Kaynak Dosyalar (C++)

> [!NOTE]
> Bu yana .NET programlama dillerinin projelerde kaynak betik dosyalarına kullanmayın kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanım [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için.
>
> Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

Terim *kaynak dosyası* gibi çeşitli dosya türü için başvuru yapabilirsiniz:

- Bir programın kaynak betiği (.rc) dosyası.

- Kaynak şablonu (.rct) dosyası.

- Mevcut tek başına bir dosya ayrı bir kaynak. Bu tür bir .rc dosyasından belirtilen bir bit eşlem, simgesi veya imleci dosyası içerir.

- Geliştirme ortamı tarafından oluşturulan bir üst bilgi dosyası. Bu türü içeren `Resource.h`, başvurduğu bir .rc dosyasından.

Kaynakları bulunan diğer dosya türleri gibi .exe, .dll ve .res dosyaları olarak ifade edilir *kaynakları*.

Çalışabileceğiniz *kaynak dosyaları* ve *kaynakları* gelen projenizin içinde. Ayrıca, geçerli projenin parçası olmayan veya Visual Studio geliştirme ortamı dışında oluşturulmuş ile çalışabilir. Örneğin, şunları yapabilirsiniz:

- İç içe geçmiş ve koşullu olarak dahil edilen kaynak dosyalarıyla birlikte çalışır.

- Var olan kaynakları güncelleştirme veya Visual C++'a dönüştürebilirsiniz.

- Grafik kaynakları için veya geçerli kaynak dosyanızı dışarı veya içeri aktarın.

- Geliştirme ortamı tarafından değiştirilemez paylaşılan veya salt okunur tanımlayıcıları (simge) içerir.

- Kaynakları düzenleme gerekmez (veya düzenlenmesi olmamalıdır), çeşitli projeler arasında paylaşılan kaynaklar gibi yürütülebilir (.exe) dosya içermektedir.

- Geliştirme ortamı tarafından desteklenmeyen kaynak türleri içerir.

Kaynaklar hakkında daha fazla bilgi için bkz. nasıl [oluşturacağınız kaynaklarda](../windows/how-to-create-a-resource-script-file.md), [kaynaklarını yönet](../windows/how-to-copy-resources.md), ve [kaynakları içeren derleme zamanında](../windows/how-to-include-resources-at-compile-time.md).

## <a name="editable-resources"></a>Düzenlenebilir kaynakları

Aşağıdaki dosya türlerini içerirler kaynakları düzenlemek için açılabilir:

| Dosya adı | Açıklama |
|---|---|
| .rc | Kaynak betik dosyalarına |
| .rct | Kaynak şablon dosyaları |
| .res | Kaynak dosyaları |
| .resx | Yönetilen kaynak dosyaları |
| .exe | Yürütülebilir dosyalar |
| .dll | Dinamik bağlantı kitaplık dosyaları |
| .bmp, .ico, .dib, .cur | Bit eşlem ve simge, araç ve imleç dosyaları |

Kaynaklar düzenlenirken, Visual Studio ortamının çalışır ve aşağıdaki dosyaları etkiler:

| Dosya adı | Açıklama |
|---|---|
| Kaynak.h | Sembol tanımlarını içeren geliştirme ortamı tarafından oluşturulan üst bilgi dosyası.<br/><br/>Bu dosya kaynak denetimine dahil. |
| Filename.APS | Hızlı yükleme için kullanılan geçerli kaynak betik dosyasını ikili sürümü.<br /><br /> Kaynak düzenleyicileri doğrudan .rc veya resource.h dosyaları okumak yok. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyaları içine derler. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar.<br/><br/>Yorum gibi sembolik olmayan bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir.<br/><br/>.Aps dosya .rc dosyasıyla eşit olduğunda .rc dosyasını yeniden oluşturulur. Örneğin, size **Kaydet**, kaynak düzenleyicisini .rc dosyasının ve resource.h dosyanın üzerine yazar. Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [kaynakları içeren derleme zamanında](../windows/how-to-include-resources-at-compile-time.md).<br/><br/>Genellikle, .aps dosya kaynak denetimine eklememelisiniz. |
| .rc | Komut dosyası için geçerli projenizdeki kaynakları içeren kaynak komut dosyası. Bu dosya, kaydettiğiniz her .aps dosyası tarafından üzerine yazılır.<br/><br/>Bu dosya kaynak denetimine dahil. |

## <a name="manifest-resources"></a>Bildirim Kaynakları

C++ Masaüstü projelerinde, bildirim, bir uygulamanın kullandığı bağımlılıkları açıklayan XML dosyaları kaynaklardır. Örneğin, Visual Studio'da bu MFC bildirim dosyası Sihirbazı tarafından oluşturulan uygulama Windows ortak Denetim dll sürümünü kullanmalıdır tanımlar:

```xml
<description>Your app description here</description>
<dependency>
    <dependentAssembly>
        <assemblyIdentity
            type="win32"
            name="Microsoft.Windows.Common-Controls"
            version="6.0.0.0"
            processorArchitecture="X86"
            publicKeyToken="6595b64144ccf1df"
            language="*"
        />
    </dependentAssembly>
</dependency>
```

Bir Windows XP veya Windows Vista Uygulama için bildirim kaynağı kullanmak için uygulamayı Windows ortak denetimleri en güncel sürümünü belirtmeniz gerekir. Yukarıdaki örnekte sürümünü kullanır `6.0.0.0`, destekleyen [Syslink denetimi](/windows/desktop/Controls/syslink-overview).

> [!NOTE]
> Yalnızca, modül başına bir bildirim kaynağı da olabilir.

Bir bildirim kaynakta yer alan bilgileri yazın ve sürümünü görüntülemek için dosyayı bir XML Görüntüleyici veya Visual Studio metin düzenleyicisi içinde açın. Bildirim kaynağı açarsanız [kaynak görünümü](../windows/resource-view-window.md), kaynak ikili biçimde açılır.

### <a name="to-open-a-manifest-resource"></a>Bildirim kaynağını açmak için

1. Projenizi Visual Studio'da açın ve gidin **Çözüm Gezgini**.

1. Genişletin **kaynak dosyaları** klasörü, ardından:

   - Metin Düzenleyicisi'nde açmak için çift tıklayın *.manifest* dosya.

   - Başka bir düzenleyicide açık olarak sağ *.manifest* seçin ve dosya **birlikte Aç**. Düzenleyicisi kullanın ve seçmek için belirttiğiniz **açık**.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak Tanımlayıcıları (Semboller)](../windows/symbols-resource-identifiers.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>