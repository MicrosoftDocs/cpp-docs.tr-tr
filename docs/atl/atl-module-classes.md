---
description: 'Daha fazla bilgi edinin: ATL modül sınıfları'
title: ATL Modül Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 16c38a6a38f4179e5846a445bd9573e7dc4500f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163307"
---
# <a name="atl-module-classes"></a>ATL Modül Sınıfları

Bu konuda, ATL 7,0 ' de yeni olan modül sınıfları ele alınmaktadır.

## <a name="ccommodule-replacement-classes"></a>CComModule değiştirme sınıfları

Daha önceki ATL sürümleri kullanıldı `CComModule` . ATL 7,0 ' de `CComModule` işlevsellik, çeşitli sınıflarla değiştirilmiştir:

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL kullanan çoğu uygulama için gereken bilgileri içerir. Modülün ve kaynak örneğinin HıNSTANCE değerini içerir.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL 'de COM sınıfları için gereken bilgileri içerir.

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL içindeki Pencereleme sınıfları için gereken bilgileri içerir.

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) Arabirim hata ayıklama desteği içerir.

- [CAtlModule](../atl/reference/catlmodule-class.md) Aşağıdaki `CAtlModule` türetilmiş sınıflar, belirli bir uygulama türünde gereken bilgileri içerecek şekilde özelleştirilir. Bu sınıflardaki çoğu üye geçersiz kılınabilir:

  - [Catldllmodület](../atl/reference/catldllmodulet-class.md) DLL uygulamalarında kullanılır. Standart dışarı aktarmalar için kod sağlar.

  - [Catlexemodüle Let](../atl/reference/catlexemodulet-class.md) EXE uygulamalarında kullanılır. Bir EXE 'de gerekli kodu sağlar.

  - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT ve Windows 2000 hizmetleri oluşturma desteği sağlar.

`CComModule` geriye dönük uyumluluk için hala kullanılabilir.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule Işlevlerini dağıtmaya yönelik nedenler

İşlevselliği `CComModule` aşağıdaki nedenlerden dolayı birkaç yeni sınıfa dağıtıldı:

- İşlevselliği ayrıntılı hale getirin `CComModule` .

   COM, Pencereleme, arabirim hata ayıklama ve uygulamaya özgü (DLL veya EXE) özellikleri için destek artık ayrı sınıflarlarlardır.

- Bu modüllerin her birinin genel örneğini otomatik olarak bildirin.

   Gerekli modül sınıflarının genel bir örneği projeye bağlanır.

- Init ve Term yöntemlerini çağırma zorunludur kaldırın.

   Init ve Term yöntemleri modül sınıfları için oluşturuculara ve yıkıcılara taşındı; artık Init ve Term çağırma gereksinimi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[Sınıfa genel bakış](../atl/atl-class-overview.md)
