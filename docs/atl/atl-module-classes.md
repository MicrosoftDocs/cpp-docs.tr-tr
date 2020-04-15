---
title: ATL Modül Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 2b72cac0da06b70a40e01fcc75da52f1678f3f64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317367"
---
# <a name="atl-module-classes"></a>ATL Modül Sınıfları

Bu konu, 7.0 TL'de yeni olan modül sınıflarını tartışır.

## <a name="ccommodule-replacement-classes"></a>Ccommodule Değiştirme Sınıfları

ATL önceki sürümlerinde kullanılır. `CComModule` ATL 7.0'da `CComModule` işlevsellik çeşitli sınıflar la değiştirilir:

- [CAtlBaseModülü](../atl/reference/catlbasemodule-class.md) ATL kullanan çoğu uygulama tarafından gerekli bilgileri içerir. Modülün HINSTANCE'ını ve kaynak örneğini içerir.

- [CAtlComModülü](../atl/reference/catlcommodule-class.md) ATL'deki COM sınıfları tarafından gerekli bilgileri içerir.

- [CAtlWinModülü](../atl/reference/catlwinmodule-class.md) ATL'deki pencere sınıfları tarafından gerekli bilgileri içerir.

- [CAtlDebugInterfacesModülü](../atl/reference/catldebuginterfacesmodule-class.md) Arabirim hata ayıklama desteği içerir.

- [CAtlModülü](../atl/reference/catlmodule-class.md) Aşağıdaki `CAtlModule`türetilmiş sınıflar, belirli bir uygulama türünde gerekli bilgileri içerecek şekilde özelleştirilmiştir. Bu sınıflardaki üyelerin çoğu geçersiz kılınabilir:

  - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL uygulamalarında kullanılır. Standart dışa aktarma için kod sağlar.

  - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE uygulamalarında kullanılır. EXE'de gerekli kodu sağlar.

  - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT ve Windows 2000 Hizmetleri oluşturmak için destek sağlar.

`CComModule`geriye dönük uyumluluk için hala kullanılabilir.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule İşlevsellik Dağıtma Nedenleri

İşlevsellik `CComModule` aşağıdaki nedenlerle birkaç yeni sınıfa dağıtıldı:

- İşlevselliği `CComModule` parçalı olarak yapın.

   COM, pencereleme, arabirim hata ayıklama ve uygulamaya özgü (DLL veya EXE) özellikleri için destek artık ayrı sınıflarda.

- Bu modüllerin her birinin genel örneğini otomatik olarak bildirin.

   Gerekli modül sınıflarının genel bir örneği projeye bağlanır.

- Init ve Terim yöntemlerini arama zorunluluğunu ortadan kaldırın.

   Init ve Terim yöntemleri modül sınıfları için yapıcılar ve yıkıcılar içine taşınmış; Artık Init ve Term'i aramaya gerek yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[Sınıfa Genel Bakış](../atl/atl-class-overview.md)
