---
title: Bildirim kaynakları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b14684adcefcf975750f64a4a7402083943b9f71
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604088"
---
# <a name="manifest-resources"></a>Bildirim Kaynakları
Bildirim kaynakları kullanan bir uygulama bağımlılıkları açıklayan XML dosyalarıdır. Örneğin, Visual Studio'da MFC Sihirbazı tarafından oluşturulan bildirim dosyası hangi sürüm 5.0 veya 6.0, Windows ortak Denetim dll uygulama kullanmalıdır tanımlar:  
  
```  
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
  
 Bir Windows XP veya Windows Vista Uygulama için bildirim kaynağı değil yalnızca uygulama Windows ortak denetimleri (v6.0, yukarıda görüldüğü gibi) en güncel sürümünü kullanın, ancak ayrıca destekler belirtir [Syslink denetimi](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 Bir bildirim kaynakta yer alan bilgileri yazın ve sürümünü görüntülemek için dosyayı bir XML Görüntüleyici veya Visual Studio'da açabilirsiniz [metin düzenleyici](http://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1). Daha fazla bilgi için [Visual Studio Metin Düzenleyicisi'nde bildirim kaynağını açma](../windows/how-to-open-a-manifest-resource.md).  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz [Walkthrough: Using Resources for LocalizationASP.NETile](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="limitations"></a>Sınırlamalar  
 Yalnızca, modül başına bir bildirim kaynağı da olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri](../mfc/controls-mfc.md)   
 [Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)