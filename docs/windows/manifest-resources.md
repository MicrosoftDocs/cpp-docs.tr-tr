---
title: "Bildirim kaynakları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- manifest resources
- resources [Visual Studio], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 56a41a7901e41f4c76fbb9fcbf5930ec97c3b866
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-resources"></a>Bildirim Kaynakları
Bildirim kaynakları uygulama kullanan bağımlılıkları açıklayan XML dosyalarıdır. Örneğin, Visual Studio'da MFC sihirbaz tarafından oluşturulan bildirim dosyası Windows ortak denetimi uygulama kullanması gereken DLL'leri, sürüm 5.0 veya 6.0 hangisinin tanımlar:  
  
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
  
 Windows XP veya Windows Vista Uygulama için bildirim kaynağı değil yalnızca uygulama Windows ortak denetimleri (v6.0, yukarıda görüldüğü gibi) en güncel sürümünü kullanabilir ancak de destekler belirtir [Syslink denetim](http://msdn.microsoft.com/library/windows/desktop/bb760706).  
  
 Bildirim kaynağı içinde yer alan bilgileri yazın ve sürümünü görüntülemek için dosyayı bir XML Görüntüleyici veya Visual Studio açabilirsiniz [metin düzenleyici](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1). Daha fazla bilgi için bkz: [Visual Studio Metin Düzenleyicisi'nde bildirim kaynağını açma](../windows/how-to-open-a-manifest-resource.md).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynakları dizeleri özelliklerine atama hakkında daha fazla bilgi için bkz: [izlenecek yol: kullanarak kaynakları yerelleştirme ASP.NETile](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="limitations"></a>Sınırlamalar  
 Yalnızca bir bildirim kaynağı modül başına olabilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri](../mfc/controls-mfc.md)   
 [Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)