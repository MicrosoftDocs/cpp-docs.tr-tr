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
ms.openlocfilehash: 463c27959b049436e29f872c966bc276c6ef5f2d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507019"
---
# <a name="resource-files-c"></a>Kaynak Dosyalar (C++)

> [!NOTE]
> .NET programlama dillerinde bulunan projeler kaynak betik dosyalarını kullanmadığından, kaynaklarınızı **Çözüm Gezgini**açmalısınız. Yönetilen projelerdeki kaynak dosyalarıyla çalışmak için [resim düzenleyicisini](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) kullanın.
>
> Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

*Kaynak dosyası* terimi, şöyle bir dizi dosya türüne başvurabilir:

- Bir programın kaynak betiği (. RC) dosyası.

- Kaynak şablonu (. rct) dosyası.

- Tek başına dosya olarak bulunan tek bir kaynak. Bu tür bir. rc dosyasından başvurulan bir bit eşlem, simge veya imleç dosyası içerir.

- Geliştirme ortamı tarafından oluşturulan bir üst bilgi dosyası. Bu tür `Resource.h` , bir. rc dosyasından başvurulan, içerir.

. Exe,. dll ve. res dosyaları gibi diğer dosya türlerinde bulunan kaynaklar *kaynak*olarak adlandırılır.

Projenizin içinden *kaynak dosyaları* ve *kaynaklarla* çalışabilirsiniz. Ayrıca, geçerli projenin parçası olmayan ya da Visual Studio 'nun geliştirme ortamı dışında oluşturulmuş olanlarla çalışabilirsiniz. Örneğin, şunları yapabilirsiniz:

- İç içe ve koşullu olarak içerilen kaynak dosyalarıyla çalışın.

- Mevcut kaynakları güncelleştirin veya Visual C++ dönüştürün.

- Grafik kaynaklarını, geçerli kaynak dosyanıza veya konumundan içeri veya dışarı aktarın.

- Geliştirme ortamı tarafından değiştirilemeyen paylaşılan veya salt tanımlı tanımlayıcıları (semboller) dahil edin.

- Farklı projeler arasında paylaşılan kaynaklar gibi, düzenleme gerektirmeyen (veya düzenlenmemelidir) dosyanın yürütülebilir (. exe) dosyasına ait kaynakları ekleyin.

- Geliştirme ortamı tarafından desteklenmeyen kaynak türlerini dahil et.

Kaynaklar hakkında daha fazla bilgi için bkz. [kaynak oluşturma](../windows/how-to-create-a-resource-script-file.md), [kaynakları yönetme](../windows/how-to-copy-resources.md)ve [derleme zamanında kaynakları ekleme](../windows/how-to-include-resources-at-compile-time.md).

## <a name="editable-resources"></a>Düzenlenebilir kaynaklar

Aşağıdaki dosya türleri, içerdikleri kaynakları düzenlemek için açılabilir:

| Dosya adı | Açıklama |
|---|---|
| . RC | Kaynak betik dosyaları |
| . rct | Kaynak şablonu dosyaları |
| . res | Kaynak dosyalar |
| .resx | Yönetilen kaynak dosyaları |
| .exe | Yürütülebilir dosyalar |
| .dll | Dinamik bağlantı kitaplığı dosyaları |
| . bmp,. ico,. dib,. cur | Bit eşlem, simge, araç çubuğu ve imleç dosyaları |

Kaynakları düzenlediğinizde, Visual Studio ortamı ile birlikte çalışarak aşağıdaki dosyaları etkiler:

| Dosya adı | Açıklama |
|---|---|
| Kaynak.h | Sembol tanımlarını içeren geliştirme ortamı tarafından oluşturulan üst bilgi dosyası.<br/><br/>Bu dosyayı kaynak denetimine ekleyin. |
| Filename. APS | Hızlı yükleme için kullanılan geçerli kaynak betiği dosyasının ikili sürümü.<br /><br /> Kaynak düzenleyicileri doğrudan. RC veya Resource. h dosyalarını okuyamıyor. Kaynak derleyicisi bunları, kaynak düzenleyicileri tarafından tüketilen. APS dosyaları olarak derler. Bu dosya bir derleme adımıdır ve yalnızca sembolik verileri depolar.<br/><br/>Normal derleme sürecinde olduğu gibi, sembolik olmayan bilgiler, derleme işlemi sırasında atılır.<br/><br/>. Aps dosyası. rc dosyası ile eşitlenmemiş olduğunda. rc dosyası yeniden oluşturulur. Örneğin, **kaydettiğinizde**, kaynak Düzenleyicisi. rc dosyasının ve Resource. h dosyasının üzerine yazar. Kaynaklardaki tüm değişiklikler. rc dosyasında dahil kalır, ancak. rc dosyasının üzerine yazıldığında açıklamalar her zaman kaybedilir. Açıklamaları koruma hakkında daha fazla bilgi için bkz. [derleme zamanında kaynakları dahil etme](../windows/how-to-include-resources-at-compile-time.md).<br/><br/>Genellikle,. AP dosyalarını kaynak denetimine eklememelisiniz. |
| . RC | Geçerli Projenizde kaynaklar için betiği içeren kaynak betik dosyası. Her kaydedişinizde, bu dosyanın üzerine. aps dosyası yazılır.<br/><br/>Bu dosyayı kaynak denetimine ekleyin. |

## <a name="manifest-resources"></a>Bildirim Kaynakları

C++ Masaüstü projelerinde, bildirim kaynakları, uygulamanın kullandığı bağımlılıkları tanımlayan XML dosyalarıdır. Örneğin, Visual Studio 'da bu MFC Sihirbazı tarafından oluşturulan bildirim dosyası, uygulamanın hangi Windows ortak denetim DLL sürümlerini kullanması gerektiğini tanımlar:

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

Bir Windows XP veya Windows Vista uygulaması için bildirim kaynağı, uygulamanın kullanması için en güncel Windows ortak denetimleri sürümünü belirtmelidir. Yukarıdaki örnek `6.0.0.0` , [Syslink denetimini](/windows/win32/Controls/syslink-overview)destekleyen sürümü kullanır.

> [!NOTE]
> Modül başına yalnızca bir bildirim kaynağına sahip olabilirsiniz.

Bir bildirim kaynağında bulunan sürümü ve tür bilgilerini görüntülemek için, dosyayı bir XML görüntüleyicisinde veya Visual Studio metin düzenleyicisinde açın. [Kaynak görünümü](./how-to-create-a-resource-script-file.md)bir bildirim kaynağı açarsanız, kaynak ikili biçimde açılır.

### <a name="to-open-a-manifest-resource"></a>Bildirim kaynağını açmak için

1. Projenizi Visual Studio 'da açın ve **Çözüm Gezgini**gidin.

1. **Kaynak dosyaları** klasörünü genişletin, ardından:

   - Metin düzenleyicisinde açmak için *. manifest* dosyasına çift tıklayın.

   - Başka bir düzenleyicide açmak için *. manifest* dosyasına sağ tıklayın ve **birlikte Aç**' ı seçin. Kullanılacak düzenleyiciyi belirtin ve **Aç**' ı seçin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak tanımlayıcıları (semboller)](../windows/symbols-resource-identifiers.md)<br/>
[Kaynak düzenleyicileri](../windows/resource-editors.md)<br/>
