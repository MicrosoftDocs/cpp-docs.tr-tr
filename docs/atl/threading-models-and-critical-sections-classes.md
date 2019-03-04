---
title: İş parçacığı oluşturma modelleri ve kritik bölüm sınıfları (ATL)
ms.date: 11/04/2016
f1_keywords:
- vc.atl.threads.models
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 862dd46100f3865b99f965a53b69edc110d6ed80
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257807"
---
# <a name="threading-models-and-critical-sections-classes"></a>İş parçacığı oluşturma modelleri ve kritik bölüm sınıfları

Aşağıdaki sınıflar, bir iş parçacığı tanımlamak modeli ve kritik bölüm:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) apartman modeli iş parçacığı havuza, COM sunucu uygular.

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) apartman modeli iş parçacığı havuza, COM sunucu uygulama için yöntemler sağlar.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) bir değişken artırma ve azaltma için iş parçacığı açısından güvenli yöntemleri sağlar. Kritik bir bölüm sağlar.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) bir değişken artırma ve azaltma için iş parçacığı açısından güvenli yöntemleri sağlar. Kritik bir bölüm sağlamaz.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) bir değişken artırma ve azaltma için yöntemler sağlar. Kritik bir bölüm sağlamaz.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) tek nesne sınıfı için uygun iş parçacığı model sınıfını belirler.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) , küresel olarak kullanılabilir bir nesne için uygun iş parçacığı modeli sınıf belirler.

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) edinme ve serbest bırakarak kritik bir bölüm için yöntemler içerir. Kritik bölüm otomatik olarak başlatılır.

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) edinme ve serbest bırakarak kritik bir bölüm için yöntemler içerir. Kritik bölüm açıkça başlatılması gerekir.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) yöntemlerini yansıtan `CComCriticalSection` kritik bölüm sağlamadan. Yöntemlere `CComFakeCriticalSection` hiçbir şey yapma.

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) için CRT iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanacaksanız kullanın.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) için bir Windows iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanmayacaksa kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../atl/atl-class-overview.md)
