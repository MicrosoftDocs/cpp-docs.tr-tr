---
title: ATL Denetim kapsamı SSS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5de6f53ca03bbab9ca42d4140a3942244db35f7
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131511"
---
# <a name="atl-control-containment-faq"></a>ATL Denetim Kapsamı SSS

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>Hangi ATL sınıfları ActiveX denetim kapsamından yararlanır?
ATL'nin denetim barındırma kodunu herhangi bir ATL sınıfları kullanmanızı gerektirmez; yalnızca oluşturabileceğiniz bir **"AtlAxWin80"** penceresinde ve gerekirse denetim barındırma API'si kullanın (daha fazla bilgi için **ATL Denetim barındırma API'si nedir**. Ancak, aşağıdaki sınıflar kapsama özellikleri daha kolay kullanılmasını.  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Saran bir **"AtlAxWin80"** penceresi, pencere oluşturmak, bir denetim oluşturma ve/veya penceresine bir denetim ekleme ve konak nesnesi üzerinde arabirim işaretçileri alınırken yöntemler sağlayacak.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Saran bir **"AtlAxWinLic80"** penceresi, pencere oluşturmak, bir denetim oluşturma ve/veya penceresine lisanslı bir denetim ekleme ve konak nesnesi üzerinde arabirim işaretçileri alınırken yöntemler sağlayacak.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|İletişim kaynağını temel ActiveX denetim sınıfları için temel sınıf olarak görev yapar. Bu tür denetimler, diğer ActiveX denetimleri içerebilir.|  
|[Caxdialogımpl](../atl/reference/caxdialogimpl-class.md)|İletişim kaynağını temel iletişim kutusu sınıfları için temel sınıf olarak görev yapar. Bu tür iletişim kutuları ActiveX denetimleri içerebilir.|  
|[CWindow](../atl/reference/cwindow-class.md)|Bir yöntem sağlar [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), dönen bir arabirim işaretçisi konak penceresinin Kimliğini belirtilen bir denetimde. Ayrıca, Windows API sarmalayıcıları kullanıma sunulan `CWindow` genellikle pencere yönetimi kolaylaştırın.|  

## <a name="what-is-the-atl-control-hosting-api"></a>ATL nedir denetim barındırma API'si?

ATL Denetim barındırma API'si, bir ActiveX denetimi kapsayıcısı görev yapacak bir pencere sağlar işlevler kümesi. Bu işlevlerin statik olabilir veya dinamik olarak kod kaynağı olarak kullanılabilir olduğu projenize bağlı ve ATL90.dll tarafından kullanıma sunulan. Denetim barındırma işlevleri, aşağıdaki tabloda listelenmiştir.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Bir konak nesnesi oluşturur, sağlanan penceresine bağlanır ve ardından varolan bir denetimi ekler.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Bir konak nesnesi oluşturur, sağlanan penceresine bağlanır ve ardından Denetim yükler.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Bir konak nesnesi oluşturur, sağlanan penceresine bağlanır ve ardından Denetim yükler (Ayrıca olay iç havuzları ayarlanmasına izin verir).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve benzer şekilde belirtilen pencerede barındırır [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|İletişim kutusu kaynağı modsuz iletişim kutusu oluşturur ve pencere tanıtıcısını döndürür.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Kalıcı bir iletişim kutusu, iletişim kutusu kaynağı oluşturur.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Döndürür **IUnknown** arayüz işaretçisinden bir pencere içinde barındırılan bir denetim.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Döndürür **IUnknown** arayüz işaretçisinden bir konak nesnesi bağlı bir pencere.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Denetim barındırma kodunu başlatır.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Denetim barındırma kodunu başlamasını iptal eder.|  
  
 `HWND` İlk üç işlev parametrelerinde varolan pencereye (yaklaşık) herhangi bir türde olması gerekir. Bu üç işlevlerden herhangi birinin açıkça çağırırsanız (genellikle, gerekmez), zaten bir konak olarak hareket eden bir pencere için bir tanıtıcı geçmeyin (Bunu yaparsanız, var olan konak nesnesi serbest olmaz).  
  
 İlk yedi işlevlerini [zaman Atlaxwinınit](reference/composite-control-global-functions.md#atlaxwininit) örtük olarak.  
  
> [!NOTE]
>  Denetim barındırma API'si ActiveX denetimi kapsamasını ATL desteği temelini oluşturur. Ancak, yoktur genellikle yararlanın ya da tam ATL sarmalayıcı sınıflar kullanılmasını sağlamak için bu işlevler doğrudan çağırmak için pek gereksinim. Daha fazla bilgi için [hangi ATL sınıfları kolaylaştırmak ActiveX denetimi kapsamasını](which-atl-classes-facilitate-activex-control-containment-q.md).  

## <a name="what-is-atlaxwin100"></a>AtlAxWin100 nedir?

`AtlAxWin100` ATL'nin denetim barındırma işlevleri sağlar bir pencere sınıf adıdır. Bu sınıfın bir örneği oluşturduğunuzda, pencere yordamı pencere ile ilgili bir ana bilgisayar nesnesi oluşturun ve pencerenin başlık olarak belirtmek denetimi ile yüklemek için Denetim barındırma API'si otomatik olarak kullanır. 

## <a name="when-do-i-need-to-call-atlaxwininit"></a>Ne zaman Atlaxwinınit çağrısı yapmam gerekir?

[Zaman Atlaxwinınit](reference/composite-control-global-functions.md#atlaxwininit) kaydeder **"AtlAxWin80"** pencere sınıf (birkaç özel pencere) için bir konak penceresini oluşturmaya çalışmadan önce bu işlevin çağrılması gerekir. Ancak, her zaman API'leri (ve bunları sınıfları) barındırma beri bu işlevi açıkça çağırmak gerekmez genellikle sizin için bu işlevi çağırın. Bu işlevinin birden çok kez çağrılması, hiçbir zarar yoktur.

## <a name="what-is-a-host-object"></a>Bir konak nesnesi nedir?

Belirli bir pencere için ATL tarafından sağlanan ActiveX denetimi kapsayıcısı temsil eden bir COM nesnesi ana nesnedir. Ana bilgisayar Denetim iletileri yansıtabilir, denetimi tarafından kullanılması için gerekli kapsayıcı arabirimleri sağlar ve kullanıma sunduğu kılabileceği kapsayıcı penceresi nesne [Iaxwinhostwindow](../atl/reference/iaxwinhostwindow-interface.md) ve [ Iaxwinambientdispatch](../atl/reference/iaxwinambientdispatch-interface.md) arabirimleri ortam denetimi yapılandırmanıza olanak sağlar.  
  
 Kapsayıcının ortam özellikleri ayarlamak için konak nesnesi kullanabilirsiniz.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Ben, tek bir pencerede birden fazla denetim barındırabilir miyim?

Tek bir ATL ana pencerede birden fazla denetimini barındırmak mümkün değildir. Her ana penceresinin (Bu ileti yansıma ve denetim başına ortam özelliklerini işlemek için basit bir mekanizma sağlar) bir zaman tam olarak bir denetim tutmak için tasarlanmıştır. Tek bir pencerede birden çok denetim görmek için kullanıcının gerekir, ancak birden çok ana bilgisayar windows penceresinin alt öğesi oluşturmak için ibarettir olur.

## <a name="can-i-reuse-a-host-window"></a>Bir konak penceresini yeniden kullanabilir miyim?

Ana bilgisayar windows yeniden önerilmez. Kodunuzun sağlamlık emin olmak için konak pencerenizi tek bir denetim ömrünü ömrünü bağlamak.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>Ne zaman AtlAxWinTerm çağrısı yapmam gerekir?

[Zaman AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) kaydını siler **"AtlAxWin80"** pencere sınıfı. (Artık ana bilgisayar windows oluşturmak için ihtiyacınız varsa) tüm mevcut ana bilgisayar windows edildikten sonra bu işlevi çağırın. Bu işlev çağırırsanız yoksa, işlem sonlandırıldığında pencere sınıfını otomatik olarak kaydı silinecek.

## <a name="hosting-activex-controls-using-atl-axhost"></a>ATL AXHost kullanarak ActiveX denetimleri barındırma

Bu bölümdeki örnek, AXHost oluşturma ve çeşitli ATL işlevleri kullanarak bir ActiveX denetimini barındırmak nasıl gösterir. Ayrıca bir erişim denetimi ve havuz olaylarını nasıl gösterir (kullanarak [Idispeventımpl](../atl/reference/idispeventimpl-class.md)) denetiminden barındırılır. Örnek, bir ana penceresinde veya bir alt pencere takvim denetimini barındırır.  
  
 Tanımı fark `USE_METHOD` simgesi. 1 ile 8 arasında değiştirmek için bu simge değerini değiştirebilirsiniz. Sembol değeri, denetimin nasıl oluşturulur belirler:  
  
-   Değerler çift sayılı için `USE_METHOD`, konak kılabileceği bir pencere oluşturma çağrısı ve bir denetim ana bilgisayara dönüştürür. Tek sayılı değerler için kod ana bilgisayar gibi davranan bir alt pencere oluşturur.  
  
-   Değerler için `USE_METHOD` 1 ile 4 arasında denetime erişme ve olaylarını indirme konak oluşturan arama gerçekleştirilir. 8 ile 5 arasındaki değerleri arabirimleri için ana bilgisayar sorgulama ve havuz bağlama.  
  
 Bir özeti aşağıda verilmiştir:  
  
|USE_METHOD|Ana bilgisayar|Erişimi denetlemek ve olay indirme|Gösterilen işlevi|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1.|Alt pencere|Bir adım|CreateControlLicEx|  
|2|Ana pencere|Bir adım|AtlAxCreateControlLicEx|  
|3|Alt pencere|Bir adım|CreateControlEx|  
|4|Ana pencere|Bir adım|AtlAxCreateControlEx|  
|5|Alt pencere|Birden çok adımı|CreateControlLic|  
|6|Ana pencere|Birden çok adımı|AtlAxCreateControlLic|  
|7|Alt pencere|Birden çok adımı|CreateControl|  
|8|Ana pencere|Birden çok adımı|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [CAxWindow2T sınıfı](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic Arabirimi](../atl/reference/iaxwinhostwindowlic-interface.md)