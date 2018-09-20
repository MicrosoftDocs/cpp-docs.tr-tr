---
title: Bildirim kaynakları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2da93d1baaf95799c7ef68d6cc854d554fbe6c47
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429571"
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

Bir bildirim kaynakta yer alan bilgileri yazın ve sürümünü görüntülemek için bir XML Görüntüleyici veya Visual Studio Metin Düzenleyicisi'nde dosyayı açabilirsiniz. Daha fazla bilgi için [Visual Studio Metin Düzenleyicisi'nde bildirim kaynağını açma](../windows/how-to-open-a-manifest-resource.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="limitations"></a>Sınırlamalar

Yalnızca, modül başına bir bildirim kaynağı da olabilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Denetimler](../mfc/controls-mfc.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)