---
title: Özellik sayfaları uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 973fb6e2a04b3f365fcbcb9d8c73fdfaf453043c
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766983"
---
# <a name="implementing-property-pages"></a>Özellik sayfaları uygulama

Özellik sayfaları olan COM nesneleri uygulayan `IPropertyPage` veya `IPropertyPage2` arabirimi. ATL özellik sayfaları aracılığıyla uygulamak için destek sağlar [ATL Özellik Sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md) içinde [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md).

ATL kullanarak bir özellik sayfası oluşturmak için:

- Oluşturun veya bir dinamik bağlantı ATL kitaplığı (DLL) sunucu projesi açın.

- Açık [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md) seçip **ATL özellik sayfası**.

- (Bir kullanıcı arabirimi olduğundan) apartman, özellik sayfası olduğundan emin olun.

- Başlık, açıklama (Doc dizesi) ve Yardım dosyasında, sayfayla ilişkilendirilecek ayarlayın.

- Denetimler, özellik sayfasının kullanıcı arabirimi olarak görev yapacak oluşturulan iletişim kutusu kaynağı ekleyin.

- Doğrulamayı gerçekleştirmek, sayfa site güncelleştirmek ya da, bir sayfayla ilişkili nesnelerini güncelleştirme için kullanıcı arabiriminde sayfanızın değişikliklerine yanıt verme. Özellikle, çağrı [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty) ne zaman kullanıcının yaptığı değişiklikler için özellik sayfası.

- İsteğe bağlı olarak geçersiz kılma `IPropertyPageImpl` aşağıdaki yönergeleri kullanarak yöntemleri.

   |Ipropertypageımpl yöntemi|Aşağıdakileri yapmak istediğinizde geçersiz kıl...|Notlar|  
   |------------------------------|----------------------------------|-----------|  
   |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|Sayfanız ve destekledikleri arabirimleri için geçirilen nesne sayısı üzerinde temel sağlamlık denetimleri gerçekleştirin.|Temel sınıf uygulamasına çağırmadan önce kendi kod yürütün. Ayarlanan nesneleri beklentilerinizle uygun olmayan, çağrı olabildiğince çabuk başarısız.|  
   |[Etkinleştirme](../atl/reference/ipropertypageimpl-class.md#activate)|(Örneğin, geçerli özellik değerlerini iletişim denetimleriyle nesnelerden ayarlamak, denetimleri dinamik olarak oluşturmak veya diğer başlatmaların) sayfanızın kullanıcı arabirimi başlatılamıyor.|Temel sınıfı, bunları güncelleştirmek denemeden önce iletişim kutusu penceresine ve tüm denetimleri oluşturmak için bir fırsat sahip olacak şekilde kodunuzu önce taban sınıf uygulamasını arayın.|  
   |[Uygula](../atl/reference/ipropertypageimpl-class.md#apply)|Özellik ayarları doğrulayın ve nesneleri güncelleştirin.|Çağrı izleme dışında herhangi bir şey yapmaz beri taban sınıf uygulamasını çağıracak şekilde gerek yoktur.|  
   |[Devre dışı bırak](../atl/reference/ipropertypageimpl-class.md#deactivate)|Pencere ile ilgili öğeleri temizleyin.|Taban sınıf uygulamasını temsil eden özellik sayfası iletişim kutusunu yok eder. İletişim kutusunu yok önce temizlemek gerekiyorsa, temel sınıfı çağırmadan önce kodunuzu eklemeniz gerekir.|

Örnek özellik sayfası için bkz: [örnek: özellik sayfası uygulama](../atl/example-implementing-a-property-page.md).

> [!NOTE]
> Özellik sayfasında konak ActiveX denetimleri için isterseniz Değiştirme Sihirbazı tarafından oluşturulan sınıfının türetme gerekecektir. Değiştirin **Cdialogımpl\<CYourClass >** ile **Caxdialogımpl\<CYourClass >** temel sınıflar listesinde.

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../atl/atl-com-property-pages.md)   
[ATLPages örnek](../visual-cpp-samples.md)
