---
title: ATL modül sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e885ef1db8f282bbdca2e8c39c3d1221d791d1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067642"
---
# <a name="atl-module-classes"></a>ATL Modül Sınıfları

Bu konu, ATL 7. 0'yeni modül sınıfları açıklar.

## <a name="ccommodule-replacement-classes"></a>CComModule değiştirme sınıfları

Önceki sürümlerinde kullanılan ATL `CComModule`. ATL 7. 0'da, `CComModule` işlevleri, çeşitli sınıfları tarafından değiştirilir:

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) ATL kullanabiliyorsanız, çoğu uygulama tarafından gerekli olan bilgileri içerir. Modül ve kaynak örneğinin HINSTANCE içerir.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) ATL COM sınıfları tarafından gerekli olan bilgileri içerir.

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) ATL Pencereleme sınıfları tarafından gerekli olan bilgileri içerir.

- [Catldebugınterfacesmodule](../atl/reference/catldebuginterfacesmodule-class.md) arabirimi hata ayıklama desteği içerir.

- [CAtlModule](../atl/reference/catlmodule-class.md) aşağıdaki `CAtlModule`-türetilmiş sınıflar belirli uygulama türde de gerekli bilgileri içeren özelleştirilmiş. Bu sınıfların çoğu üyeleri geçersiz kılınabilir:

   - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) DLL uygulamalarında kullanılır. Standart dışarı aktarmaları için kod sağlar.

   - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) EXE uygulamalarında kullanılır. Bir EXE gerekli kodu sağlar.

   - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Windows NT ve Windows 2000 hizmetleri oluşturmak için destek sağlar.

`CComModule` Geriye dönük uyumluluk için yine de kullanılabilir.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>CComModule işlevselliği dağıtmak için nedenler

İşlevselliğini `CComModule` birkaç yeni sınıfı aşağıdaki nedenlerle dağıtıldı:

- İşlevleri olun `CComModule` ayrıntılı.

     COM, Pencereleme, arabirimi hata ayıklama ve uygulamaya özgü (DLL veya EXE) özellikleri için destek ayrı sınıflarda sunulmuştur.

- Otomatik olarak bu modüllerin her biri genel örneğini bildirir.

     Gerekli modül sınıfları genel bir örneğini projeye bağlı.

- Init ve terimi yöntemleri çağırma ihtiyacını kaldırın.

     Init ve terimi yöntemleri için modül sınıfları oluşturucular ve Yıkıcılar taşındı; artık Init ve istediğiniz dönemi çağırmaya gerek yoktur.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)<br/>
[Sınıfına genel bakış](../atl/atl-class-overview.md)

