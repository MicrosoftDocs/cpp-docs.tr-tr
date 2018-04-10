---
title: ATL modül sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b254edfe75cfcdaee7ab15351f7c05c3d163e301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-module-classes"></a>ATL Modül Sınıfları
Bu konuda ATL 7. 0 ' Yeni modül sınıfları anlatılmaktadır.  
  
## <a name="ccommodule-replacement-classes"></a>CComModule değiştirme sınıfları  
 Önceki sürümlerinde kullanılan ATL `CComModule`. ATL 7. 0'da, `CComModule` işlevleri çeşitli sınıflar tarafından değiştirildi:  
  
-   [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL kullanan çoğu uygulamalar tarafından gerekli olan bilgileri içerir Modül ve kaynak örneği HINSTANCE içerir.  
  
-   [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL COM sınıfları tarafından gerekli olan bilgileri içerir  
  
-   [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL Pencereleme sınıflarda gerekli bilgileri içerir  
  
-   [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) arabirimi hata ayıklama için destek içerir.  
  
-   [CAtlModule](../atl/reference/catlmodule-class.md) aşağıdaki `CAtlModule`-türetilen sınıflar belirli uygulama türde de gerekli bilgileri içerecek şekilde özelleştirilebilir. Bu sınıfların çoğu üyeleri geçersiz kılınabilir:  
  
    -   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL uygulamalarında kullanılır. Standart dışarı aktarmalar için kod sağlar.  
  
    -   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE uygulamalarında kullanılır. Bir EXE gerekli kodu sağlar.  
  
    -   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT ve Windows 2000 hizmetleri oluşturmak için destek sağlar.  
  
 `CComModule`Geriye dönük uyumluluk için kullanılabilir durumda kalır.  
  
## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule işlevselliği dağıtma nedenleri  
 İşlevselliğini `CComModule` birkaç yeni sınıflar olarak aşağıdaki nedenlerle dağıtıldı:  
  
-   İşlevleri olun `CComModule` ayrıntılı.  
  
     COM, Pencereleme, arabirimi hata ayıklama ve uygulamaya özgü (DLL ya da EXE) özellikleri için destek ayrı sınıflarda sunulmuştur.  
  
-   Otomatik olarak bu modüllerin her biri genel örneği bildirin.  
  
     Gerekli modül sınıfları genel bir örneğini projeye bağlı.  
  
-   Init ve terim yöntemleri çağırma gerekliliğini kaldırın.  
  
     Init ve terim yöntemleri oluşturucular ve Yıkıcılar halinde modülü sınıflarını taşınmış; artık Init ve terim aramak için bir gereksinimi yoktur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [Sınıfa genel bakış](../atl/atl-class-overview.md)

