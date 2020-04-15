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
ms.openlocfilehash: 36ff3381447b46b28908522d65be9f34fe23addf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317396"
---
# <a name="atl-control-containment-faq"></a>ATL Denetim Kapsamı SSS

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>Hangi ATL Sınıfları ActiveX Denetim Kapsamından Yararlanır?

ATL'nin kontrol barındırma kodu herhangi bir ATL sınıflarını kullanmanızı gerektirmez; sadece bir **"AtlAxWin80"** pencere oluşturabilir ve gerekirse kontrol barındırma API kullanabilirsiniz (daha fazla bilgi için, **ATL Kontrol-Hosting API nedir**bakın. Ancak, aşağıdaki sınıflar çevreleme özelliklerinin kullanımını kolaylaştırır.

|Sınıf|Açıklama|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|Pencereyi oluşturmak, denetim oluşturma ve/veya pencereye denetim ekleme ve ana bilgisayar nesnesi üzerinde arabirim işaretçileri alma yöntemleri sağlayan bir **"AtlAxWin80"** penceresini sarar.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Pencereyi oluşturmak, denetim oluşturma ve/veya pencereye lisanslı denetim takma ve ana bilgisayar nesnesi üzerinde arabirim işaretçileri alma yöntemleri sağlayan bir **"AtlAxWinLic80"** penceresini sarar.|
|[CcomCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Bir iletişim kaynağına dayalı ActiveX denetim sınıfları için bir taban sınıf gibi davranır. Bu tür denetimler diğer ActiveX denetimleri içerebilir.|
|[Caxdialogımpl](../atl/reference/caxdialogimpl-class.md)|İletişim sınıfları için bir iletişim kaynağına dayalı bir taban sınıf görevi görür. Bu tür iletişim kutuları ActiveX denetimleri içerebilir.|
|[Cwindow](../atl/reference/cwindow-class.md)|Ana bilgisayar penceresinin kimliği göz önüne alındığında, denetim üzerinde bir arabirim işaretçisi döndürecek bir yöntem, [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol)sağlar. Buna ek olarak, windows API `CWindow` sarmalayıcıları genellikle pencere yönetimini kolaylaştırır.|

## <a name="what-is-the-atl-control-hosting-api"></a>ATL Denetim Barındırma API’si nedir?

ATL'nin denetim barındırma API'si, herhangi bir pencerenin ActiveX denetim kapsayıcısı olarak hareket etmesini sağlayan işlevler kümesidir. Kaynak kodu olarak kullanılabilir ve ATL90.dll tarafından açıkta olduğundan, bu işlevler statik veya dinamik olarak projenize bağlanabilir. Denetim barındırma işlevleri aşağıdaki tabloda listelenmiştir.

|İşlev|Açıklama|
|--------------|-----------------|
|[AtlAxAttachKontrol](reference/composite-control-global-functions.md#atlaxattachcontrol)|Ana bilgisayar nesnesi oluşturur, sağlanan pencereye bağlar ve varolan bir denetimi bağlar.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Ana bilgisayar nesnesi oluşturur, sağlanan pencereye bağlar, sonra denetim yükler.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Lisanslı activex denetimi oluşturur, başlatılmasını sağlar ve Belirtilen pencerede, [AtlAxCreateControl'e](reference/composite-control-global-functions.md#atlaxcreatecontrol)benzer şekilde barındırır.|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Ana bilgisayar nesnesi oluşturur, sağlanan pencereye bağlar, ardından bir denetim yükler (ayrıca olay lavabolarının ayarlanmasına izin verir).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Lisanslı activex denetimi oluşturur, başlatılmasını sağlar ve Belirtilen pencerede, [AtlAxCreateControlLic'e](reference/composite-control-global-functions.md#atlaxcreatecontrollic)benzer şekilde barındırır.|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|İletişim kaynağından modeless iletişim kutusu oluşturur ve pencere tutamacını döndürür.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Bir iletişim kaynağından modal iletişim kutusu oluşturur.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Pencerede barındırılan denetimin **IUnknown** arabirim işaretçisini döndürür.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Pencereye bağlı ana bilgisayar nesnesinin **IUnknown** arabirim işaretçisini döndürür.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Denetim barındırma kodunu niçin başlatını laştırır.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Denetim barındırma kodunu niçin başlatmaz.|

İlk `HWND` üç işlevdeki parametreler, her türde (hemen hemen) varolan bir pencere olmalıdır. Bu üç işlevden herhangi birini açıkça çağırırsanız (genellikle, bunu yapmak zorunda kalmazsınız), bir tutamacı zaten ana bilgisayar olarak hareket eden bir pencereye geçirmeyin (bunu yaparsanız, varolan ana bilgisayar nesnesi serbest bırakılmaz).

İlk yedi fonksiyon [AtlAxWinInit'i](reference/composite-control-global-functions.md#atlaxwininit) dolaylı olarak çağırır.

> [!NOTE]
> Kontrol barındırma API ActiveX kontrol kapsama için ATL desteğinin temelini oluşturur. Ancak, ATL'nin sarıcı sınıflarından yararlanır veya tam olarak kullanırsanız, bu işlevleri doğrudan aramanız genellikle çok az dır. Daha fazla bilgi için bkz: [Hangi ATL Sınıfları ActiveX Denetim Çevrelemesini Kolaylaştırın.](which-atl-classes-facilitate-activex-control-containment-q.md)

## <a name="what-is-atlaxwin100"></a>AtlAxWin100 nedir?

`AtlAxWin100`ATL'nin denetim barındırma işlevini sağlamaya yardımcı olan bir pencere sınıfının adıdır. Bu sınıfın bir örneğini oluşturduğunuzda, pencere yordamı, pencereyle ilişkili bir ana bilgisayar nesnesi oluşturmak ve pencerenin başlığı olarak belirttiğiniz denetimle yüklemek için denetim barındırma API'sini otomatik olarak kullanır.

## <a name="when-do-i-need-to-call-atlaxwininit"></a>Ne Zaman AtlAxWinInit Çağrısı Yapmam Gerekir?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) **"AtlAxWin80"** pencere sınıfını (artı birkaç özel pencere iletisi) kaydeder, bu nedenle ana bilgisayar penceresi oluşturmaya çalışmadan önce bu işlev inanılması gerekir. Ancak, barındırma API'leri (ve bunları kullanan sınıflar) genellikle bu işlevi sizin için aradığından, her zaman bu işlevi açıkça aramanız gerekmez. Bu işlevi birden fazla kez aramanın bir zararı yoktur.

## <a name="what-is-a-host-object"></a>Konak Nesnesi Nedir?

Ana bilgisayar nesnesi, belirli bir pencere için ATL tarafından sağlanan ActiveX denetim kapsayıcısını temsil eden bir COM nesnesidir. Ana bilgisayar nesnesi kapsayıcı penceresini denetime iletileri yansıtacak şekilde alt sınıflandırır, denetim tarafından kullanılmak üzere gerekli kapsayıcı arabirimleri sağlar ve denetim ortamını yapılandırmanıza olanak sağlamak için [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) ve [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) arabirimlerini ortaya çıkarır.

Kapsayıcının ortam özelliklerini ayarlamak için ana bilgisayar nesnesini kullanabilirsiniz.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Tek Bir Pencerede Birden Fazla Denetim Barındırabilir miyim?

Tek bir ATL ana bilgisayar penceresinde birden fazla denetim barındırmak mümkün değildir. Her ana bilgisayar penceresi aynı anda tam olarak bir denetim tutacak şekilde tasarlanmıştır (bu, ileti yansımasını ve kontrol başına ortam özelliklerini işlemek için basit bir mekanizma sağlar). Ancak, kullanıcının tek bir pencerede birden çok denetim görmesi gerekiyorsa, bu pencerenin alt çocukları olarak birden çok ana bilgisayar penceresi oluşturmak basit bir konudur.

## <a name="can-i-reuse-a-host-window"></a>Bir Konak Penceresini Yeniden Kullanabilir miyim?

Ana bilgisayar pencerelerini yeniden kullanmanız önerilmez. Kodunuzu sağlamlık sağlamak için, ana bilgisayar pencerenizin ömrünü tek bir denetim ömrüne bağlamanız gerekir.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>Ne Zaman AtlAxWinTerm Çağrısı Yapmam Gerekir?

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) **"AtlAxWin80"** pencere sınıfının kaydını silinir. Varolan tüm ana bilgisayar pencereleri yok edildikten sonra bu işlevi (artık ana bilgisayar pencereleri oluşturmanız gerekmiyorsa) aramalısınız. Bu işlevi aramazsanız, işlem sona erdiğinde pencere sınıfı otomatik olarak kaydolmaz.

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost Kullanarak ActiveX Denetimleri Barındırma

Bu bölümdeki örnek, AXHost'un nasıl oluşturulacagını ve çeşitli ATL işlevlerini kullanarak ActiveX denetiminin nasıl barındırılabildiğini gösterir. Ayrıca, barındırılan denetimden denetim ve lavabo olaylarına [(IDispEventImpl](../atl/reference/idispeventimpl-class.md)kullanarak) nasıl erişilir gösterilmektedir. Örnek, takvim denetimini ana pencerede veya alt pencerede barındırr.

Sembolün tanımına `USE_METHOD` dikkat edin. Bu sembolün değerini 1 ile 8 arasında değişecek şekilde değiştirebilirsiniz. Sembolün değeri denetimin nasıl oluşturulacağını belirler:

- Çift numaralı değerler `USE_METHOD`için, ana bilgisayar alt sınıfları bir pencere oluşturmak için çağrı ve bir denetim ana bilgisayara dönüştürür. Tek numaralı değerler için kod, ana bilgisayar gibi davranan bir alt pencere oluşturur.

- 1 ile `USE_METHOD` 4 arasındaki değerler için, ana bilgisayarı oluşturan çağrıda olayların denetimine ve batışına erişim gerçekleştirilir. 5 ile 8 arasındaki değerler arabirimler için ana bilgisayarı sorgular ve lavaboyu kancaya bağlar.

İşte bir özeti:

|USE_METHOD|Host|Erişim ve olay batışı kontrol|Fonksiyon gösterilmiştir|
|-----------------|----------|--------------------------------------|---------------------------|
|1|Alt pencere|Bir adım|CreateControllicex|
|2|Ana pencere|Bir adım|AtlAxCreateControlLicEx|
|3|Alt pencere|Bir adım|CreateControlEx|
|4|Ana pencere|Bir adım|AtlAxCreateControlEx|
|5|Alt pencere|Birden çok adım|CreateControllic|
|6|Ana pencere|Birden çok adım|AtlAxCreateControlLic|
|7|Alt pencere|Birden çok adım|Createcontrol|
|8|Ana pencere|Birden çok adım|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Kontrol Çevreleme SSS](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T Sınıfı](../atl/reference/caxwindow2t-class.md)<br/>
[IAxWinHostWindowLic Arabirimi](../atl/reference/iaxwinhostwindowlic-interface.md)
