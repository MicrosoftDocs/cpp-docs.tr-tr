---
title: (ATL) çift arabirim uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: 3b5363bb74a0db5b3cc5dad9bb0c0c6cb05edf15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441229"
---
# <a name="implementing-a-dual-interface"></a>Çift arabirim uygulama

Kullanan bir dual arabirimi uygulayabilir [Idispatchımpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamayı sağlar sınıfını `IDispatch` çift arabirim yöntemleri. Daha fazla bilgi için [IDispatch arabirimi uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

Bu sınıf kullanmak için:

- Bir tür kitaplığı, çift arabirim tanımlayın.

- Sınıfınıza özelleştirmesi türetilen `IDispatchImpl` (şablon bağımsız değişken olarak arabirimi ve tür kitaplığı hakkında bilgi geçirmek).

- Bir giriş (veya girişleri) çift arabirim yoluyla genele COM eşlemesi eklemek `QueryInterface`.

- Vtable arabiriminin bir parçası sınıfınızda uygulayın.

- Çalışma zamanında arabirim tanımı içeren tür kitaplığı nesnelerinizi kullanılabilir olduğundan emin olun.

## <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı

Yeni bir arabirim ve uygulamak için yeni bir sınıf oluşturmak istiyorsanız, kullanabileceğiniz [ATL Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md), ardından [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md).

## <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı

Varolan arabirimi varsa, kullanabileceğiniz [arabirim Uygulama Sihirbazı](../atl/reference/adding-a-new-interface-in-an-atl-project.md) gerekli temel sınıf, COM eşleme girişleri ve iskelet yöntem uygulamaları için varolan bir sınıf eklemek için.

> [!NOTE]
>  Tür kitaplığının birincil ve ikincil sürüm numaralarını, şablon bağımsız değişkenleri olarak geçirilir, böylece, oluşturulan taban sınıf ayarlamanız gerekebilir, `IDispatchImpl` temel sınıfı. Arabirim Uygulama Sihirbazı, tür kitaplığı sürüm numarasını denetlemez.

## <a name="implementing-idispatch"></a>IDispatch uygulama

Kullanabileceğiniz bir `IDispatchImpl` temel sınıf içindeki COM eşlemesine yalnızca uygun giriş belirterek bir dispinterface bir uygulamasını sağlamak üzere (kullanarak [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) makrosu) karşılık gelen bir çift arabirim açıklayan bir tür kitaplığı olduğu sürece. Uygulamak için oldukça yaygındır `IDispatch` bu şekilde, örneğin arabirim. ATL Basit Nesne Sihirbazı ve uygulama arabirimi hem de varsayılmaktadır uygulamak istediğiniz Sihirbazı'nı `IDispatch` bu şekilde, bu nedenle bunlar ekleyecek uygun giriş eşlenir.

> [!NOTE]
>  ATL sunar [Idispeventımpl](../atl/reference/idispeventimpl-class.md) ve [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md) uyumlu çift arabirim tanımını içeren bir tür kitaplığı gerek kalmadan, görüntü arabirimlerinde yardımcı sınıfları.

## <a name="see-also"></a>Ayrıca Bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

