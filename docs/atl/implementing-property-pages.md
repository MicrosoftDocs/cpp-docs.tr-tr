---
title: "Özellik sayfaları uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac80bdd9e38d14b53aea7b691d480272cce66e7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-property-pages"></a>Özellik sayfaları uygulama
Özellik sayfaları olan COM nesneleri uygulayan `IPropertyPage` veya **IPropertyPage2** arabirimi. ATL özellik sayfaları aracılığıyla uygulamak için destek sağlar [ATL Özellik Sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md) içinde [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md).  
  
 ATL kullanarak bir özellik sayfası oluşturmak için:  
  
-   Oluşturun veya bir ATL dinamik bağlantı kitaplığı (DLL) sunucu projesi açın.  
  
-   Açık [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md) seçip **ATL özellik sayfası**.  
  
-   Özellik sayfası (bir kullanıcı arabirimi olduğundan) iş parçacıklı grup olduğundan emin olun.  
  
-   Başlık, açıklama (belge dize) ve Yardım dosyası, sayfayla ilişkilendirilecek ayarlayın.  
  
-   Özellik sayfası kullanıcı arabirimi olarak görev yapması için oluşturulan iletişim kutusu kaynağı denetimleri ekleyin.  
  
-   Doğrulama yapmak, sayfa site güncelleştirmek ya da sayfası ile ilişkili nesneleri güncelleştirmek için sayfanın kullanıcı arabirimi değişikliklere yanıt verir. Özellikle, çağrı [IPropertyPageImpl::SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty) zaman kullanıcının yaptığı değişiklikler özellik sayfası.  
  
-   İsteğe bağlı olarak geçersiz kılma `IPropertyPageImpl` yöntemlerini aşağıdaki yönergeleri kullanarak.  
  
    |IPropertyPageImpl yöntemi|Aşağıdakileri yapmak istediğinizde geçersiz kılma...|Notlar|  
    |------------------------------|----------------------------------|-----------|  
    |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|Sayfanız ve destekledikleri arabirimler için geçirilen nesne sayısı üzerinde temel sağlamlık denetimleri gerçekleştirin.|Taban sınıfı uygulama çağrılmadan önce kendi kodunuzu yürütün. Ayarlanan nesneleri beklentilerinizi için uygun olmayan, çağrı mümkün olan en kısa sürede başarısız olması.|  
    |[Etkinleştirme](../atl/reference/ipropertypageimpl-class.md#activate)|(Örneğin, geçerli özellik değerlerini iletişim denetimleriyle nesnelerden ayarlayın, denetimleri dinamik olarak oluşturmak veya diğer başlatmaları gerçekleştirmek) sayfanızın kullanıcı arabirimi başlatılamıyor.|Taban sınıfı güncelleştirmenizi denemeden önce iletişim kutusu penceresinin ve tüm denetimleri oluşturmak için bir fırsat sahip olması kodunuzu önce temel sınıf uygulamasını arayın.|  
    |[Uygula](../atl/reference/ipropertypageimpl-class.md#apply)|Özellik ayarları doğrulayın ve nesneleri güncelleştirin.|Çağrı izleme dışında bir şey yapmaz beri temel sınıf uygulamasını çağırmak için gerek yoktur.|  
    |[Devre dışı bırakma](../atl/reference/ipropertypageimpl-class.md#deactivate)|Penceresi ile ilgili öğeleri temizleyin.|Taban sınıfı uygulama özellik sayfasını temsil eden iletişim kutusu yok eder. İletişim kutusu yok önce temizlemek gerekiyorsa, temel sınıf çağırmadan önce kodunuzu eklemeniz gerekir.|  
  
 Örnek özellik sayfası için bkz: [örnek: bir özellik sayfası uygulama](../atl/example-implementing-a-property-page.md).  
  
> [!NOTE]
>  Ana bilgisayar ActiveX denetimleri için özellik sayfasında istiyorsanız, sihirbaz tarafından oluşturulan sınıf türetme değiştirmeniz gerekir. Değiştir **Cdialogımpl\<CYourClass >** ile **CAxDialogImpl\<CYourClass >** temel sınıflar listesinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../atl/atl-com-property-pages.md)   
 [ATLPages örnek](../visual-cpp-samples.md)

