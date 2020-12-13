---
description: 'Daha fazla bilgi edinin: özellik sayfalarını uygulama'
title: Özellik sayfalarını uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- IPropertyPage2 class
- IPropertyPage class
- property pages, implementing
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
ms.openlocfilehash: 5f05831fa23eff586e85db56eca8013e0d1d2ea2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147764"
---
# <a name="implementing-property-pages"></a>Özellik sayfalarını uygulama

::: moniker range="msvc-160"

ATL Özellik sayfası Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Özellik sayfaları, veya arabirimini uygulayan COM nesneleridir `IPropertyPage` `IPropertyPage2` . ATL, [Sınıf Ekle iletişim kutusunda](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) [atl özellik sayfası Sihirbazı](../atl/reference/atl-property-page-wizard.md) aracılığıyla Özellik sayfaları uygulama desteği sağlar.

ATL kullanarak bir özellik sayfası oluşturmak için:

- ATL dinamik bağlantı kitaplığı (DLL) sunucu projesi oluşturun veya açın.

- [Sınıf Ekle iletişim kutusunu](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) açın ve **atl özellik sayfası**' nı seçin.

- Özellik sayfanızın apartman iş parçacıklı olduğundan emin olun (bir kullanıcı arabirimi olduğundan).

- Sayfanız ile ilişkilendirilecek başlık, açıklama (belge dizesi) ve yardım dosyasını ayarlayın.

- Özellik Sayfanızın kullanıcı arabirimi olarak davranacak şekilde oluşturulan iletişim kaynağına denetimler ekleyin.

- Doğrulama gerçekleştirmek, sayfa sitesini güncelleştirmek veya sayfanız ile ilişkili nesneleri güncelleştirmek için Sayfanızın kullanıcı arabirimindeki değişikliklere yanıt verin. Özellikle, Kullanıcı Özellik sayfasında değişiklik yaptığında [IPropertyPageImpl:: SetDirty](../atl/reference/ipropertypageimpl-class.md#setdirty) ' ı çağırın.

- İsteğe bağlı olarak `IPropertyPageImpl` aşağıdaki yönergeleri kullanarak yöntemleri geçersiz kılın.

   |IPropertyPageImpl yöntemi|İstediğiniz zaman geçersiz kıl...|Notlar|
   |------------------------------|----------------------------------|-----------|
   |[SetObjects](../atl/reference/ipropertypageimpl-class.md#setobjects)|Sayfanıza geçirilen nesne sayısı ve destekledikleri arabirimler üzerinde temel sağlamlık denetimleri yapın.|Temel sınıf uygulamasını çağırmadan önce kendi kodunuzu yürütün. Ayarlanmakta olan nesneler beklentilerinize uygun değilse, çağrıyı mümkün olan en kısa sürede başarısız yapmanız gerekir.|
   |[Etkinleştir](../atl/reference/ipropertypageimpl-class.md#activate)|Sayfanızın kullanıcı arabirimini başlatın (örneğin, iletişim kutusu denetimlerini nesnelerden geçerli özellik değerleriyle ayarlayın, denetimleri dinamik olarak oluşturun veya diğer başlatmalar gerçekleştirin).|Temel sınıfın, güncelleştirmeden önce iletişim penceresini ve tüm denetimleri oluşturma şansı olması için, kodunuzun önüne temel sınıf uygulamasını çağırın.|
   |[Uygula](../atl/reference/ipropertypageimpl-class.md#apply)|Özellik ayarlarını doğrulayın ve nesneleri güncelleştirin.|Çağrıyı izlemesinden ayrı bir şey yapmamadığından, temel sınıf uygulamasını çağırmanız gerekmez.|
   |[Devre dışı bırak](../atl/reference/ipropertypageimpl-class.md#deactivate)|Pencereyle ilgili öğeleri temizle.|Temel sınıf uygulama, özellik sayfasını temsil eden iletişim kutusunu yok eder. İletişim kutusu yok etmeden önce temizlemeniz gerekirse, temel sınıfı çağırmadan önce kodunuzu eklemeniz gerekir.|

Örnek özellik sayfası uygulaması için bkz. [örnek: uygulama bir özellik sayfası](../atl/example-implementing-a-property-page.md).

> [!NOTE]
> Özellik sayfanızda ActiveX denetimlerini barındırmak istiyorsanız, sihirbaz tarafından oluşturulan sınıfınızın türediğini değiştirmeniz gerekir. **Cdialogimpl \<CYourClass>** öğesini temel sınıflar listesinde **\<CYourClass> caxdialogimpl** ile değiştirin.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Özellik Sayfaları](../atl/atl-com-property-pages.md)<br/>
[ATLPages örneği](../overview/visual-cpp-samples.md)
