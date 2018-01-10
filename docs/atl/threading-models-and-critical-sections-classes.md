---
title: "İş parçacığı modelleri ve kritik bölümler sınıfları (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.threads.models
dev_langs: C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1501fe4f761b9bc8775018d6566ceff5fb0aa477
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="threading-models-and-critical-sections-classes"></a>İş parçacığı modelleri ve kritik bölümler sınıfları
Bir iş parçacığı oluşturma aşağıdaki sınıflar tanımlamak modeli ve kritik bölüm:  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) apartman modeli iş parçacığı havuza, COM sunucusu uygular.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) apartman modeli iş parçacığı havuza, COM sunucusu uygulamak için yöntemleri sağlar.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) bir değişken artırma ve azaltma için iş parçacığı yöntemleri sağlar. Önemli bir bölümü sağlar.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) bir değişken artırma ve azaltma için iş parçacığı yöntemleri sağlar. Önemli bir bölümü sağlamaz.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) bir değişken artırma ve azaltma için yöntemleri sağlar. Önemli bir bölümü sağlamaz.  
  
-   [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) tek nesne sınıfı için uygun iş parçacığı modeline sınıf belirler.  
  
-   [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) genel olarak kullanılabilir bir nesne için uygun iş parçacığı modeline sınıf belirler.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) alma ve önemli bir bölümü serbest bırakma için yöntemler içerir. Kritik bölüm otomatik olarak başlatılır.  
  
-   [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) alma ve önemli bir bölümü serbest bırakma için yöntemler içerir. Kritik bölüm açıkça başlatılması gerekir.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) yöntemlere yansıtan `CComCriticalSection` önemli bir bölümü sağlamadan. Yöntemlere `CComFakeCriticalSection` hiçbir şey yapma.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) için CRT iş parçacığı oluşturma işlevi sağlar. İş parçacığı CRT işlevleri kullanacaksanız bu sınıfı kullanın.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) için bir Windows iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanmayacaksa kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../atl/atl-class-overview.md)

