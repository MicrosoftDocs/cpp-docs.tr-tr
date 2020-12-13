---
description: 'Daha fazla bilgi edinin: Iş parçacığı modelleri ve kritik bölümler sınıfları'
title: İş parçacığı modelleri ve kritik bölümler sınıfları (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 51ad5a5f2f03bfe080395966d0c480615c49a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138287"
---
# <a name="threading-models-and-critical-sections-classes"></a>İş parçacığı modelleri ve kritik bölümler sınıfları

Aşağıdaki sınıflar bir iş parçacığı modeli ve kritik bölümü tanımlar:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) İş parçacığı havuza alınmış, Apartman modeli COM sunucusu uygular.

- [Catlautothreadmodület](../atl/reference/catlautothreadmodulet-class.md) İş parçacığı havuza alınmış, Apartman modeli COM sunucusu uygulamak için yöntemler sağlar.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) Bir değişkeni artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlar. Kritik bir bölüm sağlar.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) Bir değişkeni artırma ve azaltma için iş parçacığı açısından güvenli yöntemler sağlar. Kritik bir bölüm sağlamıyor.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) Bir değişkeni artırma ve azaltma için yöntemler sağlar. Kritik bir bölüm sağlamıyor.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) Tek bir nesne sınıfı için uygun iş parçacığı modeli sınıfını belirler.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) Genel olarak kullanılabilen bir nesne için uygun iş parçacığı modeli sınıfını belirler.

- [Ccomautocriticalhandle bölümü](../atl/reference/ccomautocriticalsection-class.md) Kritik bir bölüm alma ve serbest bırakma yöntemlerini içerir. Kritik bölümü otomatik olarak başlatılır.

- [Ccomcriticalhandle bölümü](../atl/reference/ccomcriticalsection-class.md) Kritik bir bölüm alma ve serbest bırakma yöntemlerini içerir. Kritik bölüm açık bir şekilde başlatılmalıdır.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) `CComCriticalSection` Önemli bir bölüm sağlamadan içindeki yöntemleri yansıtır. İçindeki Yöntemler `CComFakeCriticalSection` hiçbir şey yapmaz.

- [Crtthreadnitelikler](../atl/reference/crtthreadtraits-class.md) CRT iş parçacığı için oluşturma işlevi sağlar. İş parçacığı CRT işlevlerini kullanacaksanız, bu sınıfı kullanın.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Bir Windows iş parçacığı için oluşturma işlevi sağlar. İş parçacığı CRT işlevlerini kullanmayacak şekilde bu sınıfı kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../atl/atl-class-overview.md)
