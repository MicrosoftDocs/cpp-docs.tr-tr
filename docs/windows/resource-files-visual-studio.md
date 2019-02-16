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
ms.openlocfilehash: 4d56a62dfa350b3113a28355433130563464c6be
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320542"
---
# <a name="resource-files-c"></a>Kaynak Dosyalar (C++)

> [!NOTE]
> Bu yana .NET programlama dillerinin projelerde kaynak betik dosyalarına kullanmayın kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

"Kaynak dosyası" terimi, bir dizi gibi çeşitli dosya türleri için başvurabilir:

- Bir programın kaynak betiği (.rc) dosyası.

- Kaynak şablonu (.rct) dosyası.

- Mevcut tek başına bir dosya ayrı bir kaynak bit eşlemi, simgesi veya imleci dosyası gibi bir .rc dosyasından adlandırılır.

- Örneğin bir .rc dosyasından adlandırılır Resource.h, geliştirme ortamı tarafından oluşturulan bir üst bilgi dosyası.

Kaynaklar ayrıca .exe, .dll ve .res dosyaları gibi diğer dosya türleri bulunur. Projenizi ve, geçerli projenin parçası olmayan olanları kaynakları ve kaynak dosyalarıyla birlikte çalışabilir. Visual Studio geliştirme ortamında oluşturulmamış kaynak dosyalarla çalışabilirsiniz. Örneğin, şunları yapabilirsiniz:

- İç içe geçmiş ve koşullu olarak dahil edilen kaynak dosyalarıyla birlikte çalışır.

- Var olan kaynakları güncelleştirme veya Visual C++ biçimine dönüştürebilirsiniz.

- Grafik kaynakları için veya geçerli kaynak dosyanızı dışarı veya içeri aktarın.

- Geliştirme ortamı tarafından değiştirilemez paylaşılan veya salt okunur tanımlayıcıları (simge) içerir.

- Kaynakları düzenleme gerektirmeyen (veya düzenlenmesi olmamalıdır) gibi çeşitli projeler arasında paylaşılan kaynaklar, geçerli proje boyunca, yürütülebilir (.exe) dosya içermektedir.

- Geliştirme ortamı tarafından desteklenmeyen kaynak türleri içerir.

Bu bölümde ele alınmaktadır nasıl yapılır:

- [Kaynakları oluşturma](../windows/how-to-create-a-resource-script-file.md)

- [Kaynakları yönetme](../windows/how-to-copy-resources.md)

- [Derleme sırasında kaynak ekleme](../windows/how-to-include-resources-at-compile-time.md)

## <a name="editable-resource-file-types"></a>Düzenlenebilir kaynak dosya türleri

Aşağıdaki dosya türlerini içerirler kaynakları düzenlemek için açılabilir:

|Dosya adı|Açıklama|
|---------|-----------------|
|.rc|Kaynak betik dosyalarına|
|.rct|Kaynak şablon dosyaları|
|.res|Kaynak dosyaları|
|.resx|Yönetilen kaynak dosyaları|
|.exe|Yürütülebilir dosyalar|
|.dll|Dinamik bağlantı kitaplık dosyaları|
|.bmp, .ico, .dib ve .cur|Bit eşlem ve simge, araç ve imleç dosyaları.|

Visual Studio ortamının çalışır ve aşağıdaki dosyaları kaynağınızı düzenleme oturumu sırasında etkiler:

|Dosya adı|Açıklama|
|---------------|-----------------|
|Kaynak.h|Geliştirme ortamı tarafından oluşturulan üst bilgi dosyası Sembol tanımlarını içerir. (Bu dosya kaynak denetimine dahil).|
|Filename.APS|Geçerli kaynak betik dosyasını ikili sürümü; Hızlı yükleme için kullanılır.<br /><br /> Kaynak düzenleyicileri doğrudan .rc veya resource.h dosyaları okumak yok. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik olmayan bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasını ve resource.h dosyasını geçersiz kılar). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamalar her zaman kaybolacak. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [kaynakları içeren derleme zamanında](../windows/how-to-include-resources-at-compile-time.md). (Genellikle, .aps dosyayı kaynak denetimine eklememelisiniz.)|
|.rc|Komut dosyası için geçerli projenizdeki kaynakları içeren kaynak komut dosyası. Bu dosya, kaydettiğiniz her .aps dosyası tarafından üzerine yazılır. (Bu dosya kaynak denetimine dahil).|

## <a name="manifest-resources"></a>Bildirim Kaynakları

C++ Masaüstü projelerinde, bildirim, bir uygulamanın kullandığı bağımlılıkları açıklayan XML dosyaları kaynaklardır. Örneğin, Visual Studio'da MFC Sihirbazı tarafından oluşturulan bildirim dosyası hangi sürüm 5.0 veya 6.0, Windows ortak Denetim dll uygulama kullanmalıdır tanımlar:

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

Bir Windows XP veya Windows Vista Uygulama için bildirim kaynağı değil yalnızca uygulama üstündeki görülenle Windows ortak denetimleri v6.0, en son sürümünü kullanın, ancak ayrıca destekler belirtir [Syslink denetimi](/windows/desktop/Controls/syslink-overview).

Bir bildirim kaynakta yer alan bilgileri yazın ve sürümünü görüntülemek için bir XML Görüntüleyici veya Visual Studio Metin Düzenleyicisi'nde dosyayı açabilirsiniz. Bildirim kaynağı açarsanız [kaynak görünümü](../windows/resource-view-window.md), kaynak ikili biçimde açılır. Daha görüntülenebilir bir biçimde bir bildirim kaynağı içeriğini görüntülemek için kaynak açma **Çözüm Gezgini**.

### <a name="to-open-a-manifest-resource"></a>Bildirim kaynağını açmak için

1. Projenizi Visual Studio'da açın.

1. Gidin **Çözüm Gezgini** genişletin **kaynak dosyaları** klasör.

   - Metin Düzenleyicisi için .manifest dosyasını çift tıklatın.

   - Diğer düzenleyiciler, .manifest dosyasını sağ tıklatın ve seçin **birlikte Aç...** , Düzenleyicisi'ni seçin ve ardından belirtin **açık**.

> [!NOTE]
> Yalnızca, modül başına bir bildirim kaynağı da olabilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak Tanımlayıcıları (simge)](../windows/symbols-resource-identifiers.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>