---
title: Uygulama ikili arabirimi (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b4895e7b1cd0e38b33c1efe66e9070073403ee01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-a-dual-interface"></a>Çift arabirim uygulama
Çift arabirimini kullanarak uygulayabileceğiniz [IDispatchImpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamayı sağlar sınıfı `IDispatch` çift arabirim yöntemleri. Daha fazla bilgi için bkz: [IDispatch arabirimi uygulama](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
 Bu sınıf kullanmak için:  
  
-   Çift arabirim bir tür kitaplığı tanımlayın.  
  
-   Uzmanlaşması, sınıf türetin `IDispatchImpl` (şablon bağımsız değişken olarak arabirimi ve tür kitaplığı hakkında bilgi aktarmak).  
  
-   COM eşlemesi çift arabirimi aracılığıyla kullanıma sunmak için bir giriş (veya girişleri) eklemek `QueryInterface`.  
  
-   Arabirim vtable parçası sınıfınızda uygulayın.  
  
-   Çalışma zamanında arabirim tanımı içeren tür kitaplığı nesneleriniz için kullanılabilir olduğundan emin olun.  
  
## <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı  
 Yeni bir arabirimi ve uygulamak için yeni bir sınıf oluşturmak istiyorsanız, kullanabileceğiniz [ATL Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md)ve ardından [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md).  
  
## <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı  
 Varolan arabirimi varsa, kullanabileceğiniz [arabirim Uygulama Sihirbazı](../atl/reference/adding-a-new-interface-in-an-atl-project.md) gerekli temel sınıfı, COM eşleme girdilerini ve iskelet yöntemi uygulamaları varolan bir sınıfa eklemek için.  
  
> [!NOTE]
>  Tür kitaplığı birincil ve ikincil sürüm numaralarını şablon bağımsız değişken olarak geçirilen böylece oluşturulan taban sınıf ayarlamanız gerekebilir, `IDispatchImpl` temel sınıfı. Arabirim Uygulama Sihirbazı sizin için tür kitaplığı sürüm numarası denetlemez.  
  
## <a name="implementing-idispatch"></a>IDispatch uygulama  
 Kullanabileceğiniz bir `IDispatchImpl` temel COM eşleminde yalnızca uygun girdiyi belirterek bir görüntüleme arabirimi uygulaması sağlamak için sınıfı (kullanarak [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) makrosu) karşılık gelen bir çift arabirim açıklayan bir tür kitaplığı olduğu sürece. Uygulamak için oldukça yaygındır `IDispatch` bu şekilde, örneğin arabirim. ATL Basit Nesne Sihirbazı'nı ve uygulama arabirimi hem de varsayılmaktadır uygulamak istediğiniz Sihirbazı'nı `IDispatch` bu şekilde, bu nedenle bunlar eklemek uygun girdiyi eşlenir.  
  
> [!NOTE]
>  ATL sunar [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ve [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) uyumlu bir çift arabirim tanımını içeren bir tür kitaplığı gerek kalmadan dispinterfaces uygulamanıza yardımcı olmak için sınıflar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

