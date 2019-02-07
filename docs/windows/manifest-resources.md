---
title: Bildirim kaynakları (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 2d135cb2d512313f107eef7e95ec90d7972b68b4
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850196"
---
# <a name="manifest-resources-c"></a>Bildirim kaynakları (C++)

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

Bir Windows XP veya Windows Vista Uygulama için bildirim kaynağı değil yalnızca uygulama Windows ortak denetimleri (v6.0, yukarıda görüldüğü gibi) en güncel sürümünü kullanın, ancak ayrıca destekler belirtir [Syslink denetimi](/windows/desktop/Controls/syslink-overview).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

Bir bildirim kaynakta yer alan bilgileri yazın ve sürümünü görüntülemek için bir XML Görüntüleyici veya Visual Studio Metin Düzenleyicisi'nde dosyayı açabilirsiniz. Bildirim kaynağı açarsanız [kaynak görünümü](../windows/resource-view-window.md), kaynak ikili biçimde açılır. Daha görüntülenebilir bir biçimde bir bildirim kaynağı içeriğini görüntülemek için kaynak açma **Çözüm Gezgini**.

## <a name="to-open-a-manifest-resource-in-the-text-editor"></a>Bildirim kaynağı Metin Düzenleyicisi'nde açmak için

1. Proje Aç ile **Çözüm Gezgini**, genişletme **kaynak dosyaları** klasör.

1. .Manifest dosyasını çift tıklatın.

   Bildirim kaynağınızı açılır **metin düzenleyici**.

## <a name="to-open-a-manifest-resource-in-another-editor"></a>Bildirim kaynağı başka bir düzenleyicide açın.

1. İçinde **Çözüm Gezgini**.manifest dosyasını sağ tıklatın ve seçin **birlikte Aç...**  kısayol menüsünden.

1. İçinde **birlikte Aç** iletişim kutusunda, seçin ve istediğiniz düzenleyici belirtmenize **açık**.

## <a name="limitations"></a>Sınırlamalar

Yalnızca, modül başına bir bildirim kaynağı da olabilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Denetimler](../mfc/controls-mfc.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)