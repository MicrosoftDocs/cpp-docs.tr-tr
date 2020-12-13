---
description: 'Daha fazla bilgi edinin: Dual Interface uygulama'
title: Çift arabirim uygulama (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: e20bbe293cb7d6e7ae0f4d0482f1003571178ab9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147803"
---
# <a name="implementing-a-dual-interface"></a>Çift arabirim uygulama

İkili bir arabirimde yöntemlerin varsayılan bir uygulamasını sağlayan [IDispatchImpl](../atl/reference/idispatchimpl-class.md) sınıfını kullanarak çift bir arabirim uygulayabilirsiniz `IDispatch` . Daha fazla bilgi için bkz. [IDispatch arabirimini uygulama](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface).

Bu sınıfı kullanmak için:

- Bir tür kitaplığında çift arabiriminizi tanımlayın.

- Bir özelleştirmede sınıfınızı türetirsiniz `IDispatchImpl` (arabirim ve tür kitaplığı ile ilgili bilgileri şablon bağımsız değişkenleri olarak geçirin).

- Dual Interface 'i aracılığıyla göstermek için COM haritasına bir giriş (veya girdiler) ekleyin `QueryInterface` .

- Sınıfınıza arabirimin vtable bölümünü uygulayın.

- Arabirim tanımını içeren tür kitaplığının, çalışma zamanında nesneleriniz için kullanılabilir olduğundan emin olun.

## <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı

Yeni bir arabirim ve bunu uygulamak için yeni bir sınıf oluşturmak istiyorsanız, [atl sınıf Ekle iletişim kutusunu](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box)ve ardından [atl basit nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)' nı kullanabilirsiniz.

## <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı

Mevcut bir arabiriminiz varsa, gerekli temel sınıfı, COM eşleme girişlerini ve çatı yöntemi uygulamalarını mevcut bir sınıfa eklemek için [arabirim uygulama Sihirbazı](../atl/reference/adding-a-new-interface-in-an-atl-project.md) ' nı kullanabilirsiniz.

> [!NOTE]
> Tür kitaplığının büyük ve küçük sürüm numaralarının temel sınıfınıza şablon bağımsız değişkeni olarak geçirilmesi için oluşturulan temel sınıfı ayarlamanız gerekebilir `IDispatchImpl` . Arabirim uygulama Sihirbazı sizin için tür kitaplığı sürüm numarasını denetlemez.

## <a name="implementing-idispatch"></a>IDispatch uygulama

`IDispatchImpl`Kendisine karşılık gelen bir çift arabirimi açıklayan bir tür kitaplığınız olduğu sürece, com haritasında uygun girişi belirterek ( [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) makrosunu kullanarak) bir dispınterface uygulamasının uygulanmasını sağlamak için bir temel sınıf kullanabilirsiniz. `IDispatch`Arabirimin bu şekilde uygulanması oldukça yaygındır. Örneğin,. ATL basit nesne Sihirbazı ve uygulama arabirimi Sihirbazı her ikisi de bu şekilde uygulamak istediğinizi varsaymaktadır `IDispatch` , böylece haritaya uygun girdiyi ekler.

> [!NOTE]
> ATL, uyumlu bir çift arabirimin tanımını içeren bir tür kitaplığı gerektirmeden dispınterfaces uygulamanıza yardımcı olmak üzere [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ve [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) sınıfları sunar.

## <a name="see-also"></a>Ayrıca bkz.

[Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
