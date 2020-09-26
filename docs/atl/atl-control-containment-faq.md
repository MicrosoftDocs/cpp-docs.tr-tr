---
title: ATL Denetim Kapsamı SSS
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 693617589f157d352972485396777cec587a5b8f
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352706"
---
# <a name="atl-control-containment-faq"></a>ATL Denetim Kapsamı SSS

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>Hangi ATL Sınıfları ActiveX Denetim Kapsamından Yararlanır?

ATL 'nin denetim barındırma kodu herhangi bir ATL sınıfı kullanmanızı gerektirmez; Basitçe bir **"AtlAxWin80"** penceresi oluşturabilir ve gerekirse DENETIM barındırma API 'sini kullanabilirsiniz (daha fazla bilgi için bkz. **atl Denetim barındırma API nedir?**. Ancak, aşağıdaki sınıflar kapsama özelliklerinin kullanımını daha kolay hale getirir.

|Sınıf|Açıklama|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|Pencereyi oluşturma, denetim oluşturma ve/veya pencereye bir denetim ekleme ve ana bilgisayar nesnesine arabirim işaretçileri alma yöntemleri sağlayan bir **"AtlAxWin80"** penceresini sarmalar.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Pencereyi oluşturmak, bir denetim oluşturmak ve/veya lisanslı bir denetimi pencereye eklemek ve ana bilgisayar nesnesine arabirim işaretçileri almak için yöntemler sağlayan bir **"AtlAxWinLic80"** penceresini sarmalar.|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|, Bir iletişim kaynağını temel alan ActiveX denetim sınıfları için temel sınıf işlevi görür. Bu denetimler, diğer ActiveX denetimlerini içerebilir.|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|İletişim kutusu kaynağını temel alan iletişim sınıfları için temel sınıf işlevi görür. Bu tür iletişimler, ActiveX denetimleri içerebilir.|
|[CWindow](../atl/reference/cwindow-class.md)|, Ana bilgisayar penceresinin KIMLIĞI verildiğinde bir denetimde bir arabirim işaretçisi döndüren [Getdlcontrol](../atl/reference/cwindow-class.md#getdlgcontrol)metodunu sağlar. Buna ek olarak, genellikle pencere yönetimini de açığa çıkarılan Windows API sarmalayıcıları `CWindow` daha kolay hale getirir.|

## <a name="what-is-the-atl-control-hosting-api"></a>ATL Denetim Barındırma API’si nedir?

ATL 'nin denetim barındırma API 'SI, herhangi bir pencerenin bir ActiveX Denetim kapsayıcısı olarak davranmasına izin veren işlevlerin bir kümesidir. Bu işlevler, kaynak kodu olarak kullanılabilir ve ATL90.dll tarafından kullanıma sunulduğundan, projenize statik veya dinamik olarak bağlanabilir. Denetim barındırma işlevleri aşağıdaki tabloda listelenmiştir.

|İşlev|Açıklama|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Bir konak nesnesi oluşturur, onu sağlanan pencereye bağlar, sonra var olan bir denetimi iliştirir.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Bir konak nesnesi oluşturur, onu sağlanan pencereye bağlar ve sonra bir denetim yükler.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)gibi belirtilen pencerede barındırır.|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Bir konak nesnesi oluşturur, onu sağlanan pencereye bağlar, sonra da bir denetim yükler (Ayrıca olay havuzları ayarlamaya izin verir).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)gibi belirtilen pencerede barındırır.|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|İletişim kutusu kaynağından kalıcı olmayan iletişim kutusu oluşturur ve pencere tanıtıcısını döndürür.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|İletişim kutusu kaynağından kalıcı iletişim kutusu oluşturur.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Bir pencerede barındırılan denetimin **IUnknown** arabirim işaretçisini döndürür.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Pencereye bağlı konak nesnesinin **IUnknown** arabirim işaretçisini döndürür.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Denetim barındırma kodunu başlatır.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Denetim barındırma kodunu başlatır.|

`HWND`İlk üç fonksiyondaki parametreler, herhangi bir türden (neredeyse) mevcut bir pencere olmalıdır. Bu üç işlevden herhangi birini açık bir şekilde çağırırsanız (genellikle, uygulamanız gerekmez), bir tutamacı zaten ana bilgisayar olarak davranan bir pencereye geçirmeyin (varsa, var olan ana bilgisayar nesnesi serbest bırakılmaz).

İlk yedi işlev [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) öğesini örtülü olarak çağırır.

> [!NOTE]
> Denetim barındırma API 'SI, ATL 'nin ActiveX denetim kapsamı desteğinin temelini oluşturur. Ancak, ATL 'nin sarmalayıcı sınıflarının avantajlarından faydalanarak veya tam olarak kullanılması durumunda bu işlevleri doğrudan çağırmak için çok az gereksinim vardır. Daha fazla bilgi için bkz. [HANGI atl sınıfları ActiveX denetim kapsamasını kolaylaştırır](#which-atl-classes-facilitate-activex-control-containment).

## <a name="what-is-atlaxwin100"></a>AtlAxWin100 nedir?

`AtlAxWin100` , ATL 'ın denetim barındırma işlevselliği sağlamaya yardımcı olan bir pencere sınıfının adıdır. Bu sınıfın bir örneğini oluşturduğunuzda pencere yordamı, pencereyle ilişkili bir konak nesnesi oluşturmak ve bunu pencerenin başlığı olarak belirttiğiniz denetimle yüklemek için denetim barındırma API 'sini otomatik olarak kullanır.

## <a name="when-do-i-need-to-call-atlaxwininit"></a>Ne Zaman AtlAxWinInit Çağrısı Yapmam Gerekir?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) , **"AtlAxWin80"** pencere sınıfını (artı birkaç özel pencere iletisi) kaydettirir, bu nedenle bir konak penceresi oluşturmayı denemeden önce bu işlevin çağrılması gerekir. Ancak, barındırma API 'Leri (ve bunları kullanan sınıflar) genellikle sizin için çağırdığından bu işlevi her zaman açıkça çağırmanız gerekmez. Bu işlevi birden çok kez çağırmaya bir zarar yok.

## <a name="what-is-a-host-object"></a>Konak Nesnesi Nedir?

Ana bilgisayar nesnesi, belirli bir pencere için ATL tarafından sağlanan ActiveX denetim kapsayıcısını temsil eden bir COM nesnesidir. Ana bilgisayar nesnesi kapsayıcı penceresinin alt sınıflarını denetime iletileri yansıtabilmesi için, denetim tarafından kullanılacak gerekli kapsayıcı arabirimlerini sağlar ve denetimin ortamını yapılandırmanıza izin vermek için [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) ve [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) arabirimlerini kullanıma sunar.

Kapsayıcının çevresel özelliklerini ayarlamak için ana bilgisayar nesnesini kullanabilirsiniz.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Tek Bir Pencerede Birden Fazla Denetim Barındırabilir miyim?

Tek bir ATL ana bilgisayar penceresinde birden fazla denetim barındırmak mümkün değildir. Her ana bilgisayar penceresi tek seferde tam olarak bir denetim tutmak üzere tasarlanmıştır (Bu, ileti yansıma ve denetim başına çevresel özellikleri işlemek için basit bir mekanizmaya olanak sağlar). Bununla birlikte, kullanıcının tek bir pencerede birden çok denetimi görmesini istiyorsanız, bu pencerenin alt öğesi olarak birden çok konak penceresi oluşturmanın basit bir önemi vardır.

## <a name="can-i-reuse-a-host-window"></a>Bir Konak Penceresini Yeniden Kullanabilir miyim?

Ana bilgisayar pencerelerini yeniden kullanmanız önerilmez. Kodunuzun sağlamlığını sağlamak için, ana bilgisayar pencerenizin yaşam süresini tek bir denetimin kullanım süresine bağlayın.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>Ne Zaman AtlAxWinTerm Çağrısı Yapmam Gerekir?

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) , **"AtlAxWin80"** pencere sınıfının kaydını siler. Tüm mevcut konak pencereleri yok edildikten sonra bu işlevi (artık konak pencereleri oluşturmanız gerekmiyorsa) çağırmalısınız. Bu işlevi çağırmazsanız, işlem sonlandırıldığında pencere sınıfının kaydı otomatik olarak kaldırılır.

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost Kullanarak ActiveX Denetimleri Barındırma

Bu bölümdeki örnek, AXHost oluşturma ve çeşitli ATL işlevleri kullanılarak ActiveX denetiminin nasıl barındıralınacağını gösterir. Ayrıca, barındırılan denetimden denetim ve havuz olaylarına ( [IDispEventImpl](../atl/reference/idispeventimpl-class.md)kullanılarak) nasıl erişim yapılacağı gösterilmektedir. Örnek, Takvim denetimini ana pencerede veya bir alt pencerede barındırır.

Simgenin tanımına dikkat edin `USE_METHOD` . 1 ile 8 arasında değişiklik yapmak için bu sembolün değerini değiştirebilirsiniz. Simgenin değeri, denetimin nasıl oluşturulacağını belirler:

- Çift sayılı değerler için `USE_METHOD` , ana bilgisayar alt sınıfları oluşturma ve bir denetim konağına dönüştürme çağrısı. Tek sayılı değerler için, kod, ana bilgisayar görevi gören bir alt pencere oluşturur.

- `USE_METHOD`1 ile 4 arasındaki değerler için, ana bilgisayarı da oluşturan çağrıda denetim ve olayların erişimine erişim elde edilir. 5 ile 8 arasındaki değerler, arabirimler için Konağı sorgular ve havuzu barındırır.

Özet:

|USE_METHOD|Ana bilgisayar|Erişimi ve olay denetimini denetleme|İşlev gösterilmiştir|
|-----------------|----------|--------------------------------------|---------------------------|
|1|Alt pencere|Bir adım|CreateControlLicEx|
|2|Ana pencere|Bir adım|AtlAxCreateControlLicEx|
|3|Alt pencere|Bir adım|CreateControlEx|
|4|Ana pencere|Bir adım|AtlAxCreateControlEx|
|5|Alt pencere|Birden çok adım|Createcontrollik|
|6|Ana pencere|Birden çok adım|AtlAxCreateControlLic|
|7|Alt pencere|Birden çok adım|CreateControl|
|8|Ana pencere|Birden çok adım|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Denetim kapsama hakkında SSS](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T sınıfı](../atl/reference/caxwindow2t-class.md)<br/>
[Iaxwinhostwindowlik arabirimi](../atl/reference/iaxwinhostwindowlic-interface.md)
