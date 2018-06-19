---
title: MFC ve ATL | Microsoft Docs
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 31b1a3a8-4154-4c4a-af10-fafc23ecdc5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 081414d3835a8a6efcc831b6c303b774361b743b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347740"
---
# <a name="mfc-and-atl"></a>MFC ve ATL
Microsoft Foundation sınıfları (MFC) yerel Masaüstü uygulamaları hızlı geliştirme için Win32 nesne yönelimli bir C++ kapsayıcı sağlar. Etkin Şablon kitaplığı (ATL), COM Geliştirme basitleştirir ve ActiveX denetimleri oluşturmak için yaygın kullanılan bir sarmalayıcı kitaplıktır.  
  
MFC veya ATL programı Visual Studio Community sürümü veya üzeri oluşturabilirsiniz. Express sürümleri MFC ve ATL desteklemez 

Visual Studio 2015 ' te Visual C++ isteğe bağlı bir bileşenidir ve MFC ve ATL bileşenleri isteğe bağlı alt Visual C++ altında bileşenlerdir. Visual Studio'ı ilk yüklediğinizde bu bileşenlerin seçmezseniz bir MFC ya da ATL projesi oluşturma veya açma girişiminde ilk kez yüklerken istenir.  

Visual Studio 2017 ve daha sonra MFC ve ATL isteğe bağlı alt altında bileşenleridir **C++ ile masaüstü geliştirme** Visual Studio yükleyici program iş yükü. ATL desteği MFC olmadan yükleyebilirsiniz veya birleştirilmiş MFC ve ATL desteği (MFC üzerinde ATL bağlıdır). İş yükleri ve bileşenleri hakkında daha fazla bilgi için bkz: [yükleme Visual Studio 2017](/visualstudio/install/install-visual-studio).
  
## <a name="related-articles"></a>İlgili Makaleler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[MFC Masaüstü Uygulamaları](../mfc/mfc-desktop-applications.md)|C++'ta GUI uygulamalarının hızlı geliştirme etkinleştirmek için Win32 üzerinden basit bir nesne yönelimli sarmalayıcı Microsoft Foundation sınıflar sağlar.|  
|[ATL COM Masaüstü Bileşenleri](../atl/atl-com-desktop-components.md)|Sınıf şablonları ATL sağlar ve c++ COM nesneleri oluşturma işlemini basitleştirmek için diğer kullanım oluşturur.|  
|[ATL/MFC sınıfları paylaşılan](../atl-mfc-shared/atl-mfc-shared-classes.md)|İçin başvuran [CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md) ve MFC ve ATL tarafından paylaşılan diğer sınıflar|  
|[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)|Kaynak Düzenleyici dizeler, görüntüler ve iletişim kutuları gibi UI kaynakları düzenlemenize olanak tanır.|  
|[Visual C++](../visual-cpp-in-visual-studio.md)|MSDN Kitaplığı'ndaki tüm C++ içerik için üst konu.|