---
title: ATL sınıfları ve yapıları | Microsoft Docs
ms.date: 05/03/2018
helpviewer_keywords:
- classes [C++], ATL
- ATL, classes
ms.assetid: 7da42e2d-ac84-4506-92bd-502a86d68bdc
ms.openlocfilehash: 561d6cb41ca066f5a2435b4eb1e8710ccaa99ea1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62248946"
---
# <a name="atl-classes-and-structs"></a>ATL sınıfları ve yapıları

Aşağıdaki sınıflar ve yapılar Etkin Şablon kitaplığı (ATL) içerir. Belirli bir sınıfın kategoriye göre bulmak için bkz: [ATL sınıfına genel bakış](../../atl/atl-class-overview.md).

|Sınıf / yapı|Açıklama|Üst bilgi dosyası|
|-----------|-----------------|-----------------|
|[ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)|Bir yazıcı, meta dosyası ya da ActiveX denetimi gibi çeşitli hedeflere işleme için kullanılan bilgileri içerir.|atlctl.h|
|[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)|ATL Pencereleme kodunda sınıfı örneği verileri içerir|atlbase.h|
|[_ATL_BASE_MODULE70](../../atl/reference/atl-base-module70-structure.md)|ATL kullanan herhangi bir proje tarafından kullanılan|atlbase.h|
|[_ATL_COM_MODULE70](../../atl/reference/atl-com-module70-structure.md)|ATL COM ile ilgili kod tarafından kullanılan| atlbase.h|
|[_ATL_FUNC_INFO](../../atl/reference/atl-func-info-structure.md)|Bir yöntem veya özellik üzerinde bir dispinterface açıklamak için kullanılan tür bilgilerini içerir.|atlcom.h|
|[_ATL_MODULE70](../../atl/reference/atl-module70-structure.md)|Her ATL modülü tarafından kullanılan verileri içerir.|atlbase.h|
|[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)|ATL Pencereleme kod tarafından kullanılan|atlbase.h|
|[CA2AEX](../../atl/reference/ca2aex-class.md)|Bu sınıf, dize dönüşüm makroları CA2TEX ve CT2AEX ve typedef CA2A tarafından kullanılır.|atlconv.h|
|[CA2CAEX](../../atl/reference/ca2caex-class.md)|Bu sınıf, dize dönüşüm makroları CA2CTEX ve CT2CAEX ve typedef CA2CA tarafından kullanılır.|atlconv.h|
|[CA2WEX](../../atl/reference/ca2wex-class.md)|Bu sınıf, dize dönüşüm makroları CA2TEX, CA2CTEX, CT2WEX ve CT2CWEX ve typedef CA2W tarafından kullanılır.|atlconv.h|
|[CAccessToken](../../atl/reference/caccesstoken-class.md)|Bir erişim belirteci için bir sarmalayıcı sınıftır.|atlsecurity.h|
|[CAcl](../../atl/reference/cacl-class.md)|Bir ACL (erişim denetim listesi) yapısı için bir sarmalayıcı sınıftır.|atlsecurity.h|
|[CAdapt](../../atl/reference/cadapt-class.md)|Bu şablon, nesnenin adresi dışında bir öğe döndürmek üzere address-of işlecini yeniden tanımlayan sınıfları sarmalamak için kullanılır.|atlcomcli.h|
|[CAtlArray](../../atl/reference/catlarray-class.md)|Bu sınıf, bir dizi nesnesi uygular.|atlcoll.h|
|[CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)|Bu sınıf, apartman modeli iş parçacığı havuza, COM sunucu uygular.|atlbase.h|
|[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)|Bu sınıf, apartman modeli iş parçacığı havuza, COM sunucu uygulama için yöntemler sağlar.|atlbase.h|
|[CAtlBaseModule](../../atl/reference/catlbasemodule-class.md)|Bu sınıf, her bir ATL projesinde oluşturulur.|atlcore.h|
|[CAtlComModule](../../atl/reference/catlcommodule-class.md)|Bu sınıf, bir COM sunucusu modülü uygular.|atlbase.h|
|[Catldebugınterfacesmodule](../../atl/reference/catldebuginterfacesmodule-class.md)|Bu sınıf, hata ayıklama arabirimleri için destek sağlar.|atlbase.h|
|[CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)|Bu sınıf, bir DLL için modül temsil eder.|atlbase.h|
|[CAtlException](../../atl/reference/catlexception-class.md)|Bu sınıf, ATL istisna tanımlar.|atlexcept.h|
|[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)|Bu sınıf, bir uygulama için modülü temsil eder.|atlbase.h|
|[CAtlFile](../../atl/reference/catlfile-class.md)|Bu sınıf, dosya işleme API Windows çevresinde ince bir sarmalayıcı sağlar.|atlfile.h|
|[CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)|Bu sınıfın temsil yöntemleri için bir atama işleci ekleyerek bir bellek işlemeli dosya [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).|atlfile.h|
|[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)|Bu sınıf, bir bellek işlemeli dosya temsil eder.|atlfile.h|
|[CAtlList](../../atl/reference/catllist-class.md)|Bu sınıf, oluşturmak ve bir liste nesnesi yönetmek için yöntemler sağlar.|atlcoll.h|
|[CAtlMap](../../atl/reference/catlmap-class.md)|Bu sınıf, oluşturmak ve bir harita nesnesi yönetmek için yöntemler sağlar.|atlcoll.h|
|[CAtlModule](../../atl/reference/catlmodule-class.md)|Bu sınıf, birkaç ATL modül sınıfları tarafından kullanılan yöntemleri sağlar.|atlbase.h|
|[CAtlModuleT](../../atl/reference/catlmodulet-class.md)|Bu sınıf bir ATL modül uygular.|atlbase.h|
|[CAtlPreviewCtrlImpl](../../atl/reference/catlpreviewctrlimpl-class.md)|Bu sınıf bir kabuk tarafından sağlanan Zengin Önizleme için barındırıcı penceresine yerleştirilen bir pencere ATL uygulamasıdır.|atlpreviewctrlimpl.h|
|[CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md)|Bu sınıf, bir hizmet uygular.|atlbase.h|
|[CAtlTemporaryFile](../../atl/reference/catltemporaryfile-class.md)|Bu sınıf, oluşturulmasını ve kullanımını geçici bir dosya için yöntemler sağlar.|atlfile.h|
|[CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)|Bu sınıf, çekirdek işlem yöneticisi (KTM) işlevleri için bir sarmalayıcı sağlar.|atltransactionmanager.h|
|[CAtlWinModule](../../atl/reference/catlwinmodule-class.md)|Bu sınıf, ATL Pencereleme bileşenleri için destek sağlar.|atlbase.h|
|[CAutoPtr](../../atl/reference/cautoptr-class.md)|Bu sınıf, bir akıllı işaretçi nesnesinin temsil eder.|atlbase.h|
|[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)|Bu sınıf, bir akıllı işaretçiler dizisi oluştururken kullanışlı yöntemler sağlar.|atlbase.h|
|[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)|Bu sınıf, akıllı işaretçiler koleksiyonları oluştururken yöntemleri statik işlevler ve tür tanımları yararlı sağlar.|atlcoll.h|
|[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)|Bu sınıf, akıllı işaretçiler listesini oluştururken kullanışlı yöntemler sağlar.|atlcoll.h|
|[CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)|Bu sınıf, vektör kullanarak yeni bir akıllı işaretçi nesnesinin temsil eder ve delete işleçleri.|atlbase.h|
|[CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md)|Bu sınıf, yöntem, statik işlevler ve tür tanımları akıllı işaretçiler kullanarak vektör yeni koleksiyon oluşturma ve delete işleçleri yararlı sağlar.|atlcoll.h|
|[Caxdialogımpl](../../atl/reference/caxdialogimpl-class.md)|Bu sınıf, bir iletişim kutusu (kalıcı veya kısıtlayıcı olmayan) barındıran ActiveX denetimlerini uygular.|atlwin.h|
|[CAxWindow](../../atl/reference/caxwindow-class.md)|Bu sınıf, bir ActiveX denetimi barındırma pencere yönlendirmeye yönelik yöntemleri sağlar.|atlwin.h|
|[CAxWindow2T](../../atl/reference/caxwindow2t-class.md)|Bu sınıf, bir ActiveX denetimini barındırır ve ayrıca lisanslı bir ActiveX denetimlerini barındırma desteği olan bir pencere yönlendirmeye yönelik yöntemleri sağlar.|atlwin.h|
|[CBindStatusCallback](../../atl/reference/cbindstatuscallback-class.md)|Bu sınıfın uyguladığı `IBindStatusCallback` arabirimi.|atlctl.h|
|[CComAggObject](../../atl/reference/ccomaggobject-class.md)|Bu sınıfın uyguladığı [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) toplanan nesne için.|atlcom.h|
|[CComAllocator](../../atl/reference/ccomallocator-class.md)|Bu sınıf, COM bellek yordamları kullanarak bellek yönetmek için yöntemler sağlar.|atlbase.h|
|[CComApartment](../../atl/reference/ccomapartment-class.md)|Bu sınıf, bir iş parçacığı havuza EXE modülü bir grupta yönetmek için destek sağlar.|atlbase.h|
|[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)|Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.|atlcore.h|
|[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)|ATL 7. 0'den itibaren `CComAutoThreadModule` artık kullanılmıyor: bkz [ATL modülleri](../../atl/atl-module-classes.md) daha fazla ayrıntı için.|atlbase.h|
|[CComBSTR](../../atl/reference/ccombstr-class.md)|BSTR'lerin için bir sarmalayıcı sınıftır.|atlbase.h|
|[CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)|Bu sınıfın uyguladığı [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) bölünmüş arabirim.|atlcom.h|
|[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)|Bu sınıfın uyguladığı [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirimi.|atlcom.h|
|[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)|Bu sınıfın uyguladığı [IClassFactory2](/windows/desktop/api/ocidl/nn-ocidl-iclassfactory2) arabirimi.|atlcom.h|
|[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)|Bu sınıfın uyguladığı [IClassFactory](/windows/desktop/api/unknwnbase/nn-unknwnbase-iclassfactory) arabirim ve nesnelerin içinde birden çok apartmanlar oluşturulmasına izin verir.|atlcom.h|
|[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)|Bu sınıfın türetildiği [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ve kullandığı [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) tek bir nesne oluşturmak için.|atlcom.h|
|[CComCoClass](../../atl/reference/ccomcoclass-class.md)|Bu sınıf, bir sınıfın örneklerini oluşturmak ve özelliklerini almak için yöntemler sağlar.|atlcom.h|
|[CComCompositeControl](../../atl/reference/ccomcompositecontrol-class.md)|Bu sınıf, bileşik denetim uygulamak için gereken yöntemleri sağlar.|atlctl.h|
|[CComContainedObject](../../atl/reference/ccomcontainedobject-class.md)|Bu sınıfın uyguladığı [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) sahibi nesnenin temsilci tarafından `IUnknown`.|atlcom.h|
|[CComControl](../../atl/reference/ccomcontrol-class.md)|Bu sınıf, oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar.|atlctl.h|
|[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)|Bu sınıf, oluşturmak ve ATL denetimleri yönetmek için yöntemler sağlar.|atlctl.h|
|[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)|Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.|atlcore.h|
|[CComCritSecLock](../../atl/reference/ccomcritseclock-class.md)|Bu sınıf, kilitleme ve kritik bölüm nesne kilidi kaldırma için yöntemler sağlar.|atlbase.h|
|[CComCurrency](../../atl/reference/ccomcurrency-class.md)|Bu sınıf, oluşturmak ve bir para birimi nesnesi yönetme için yöntemleri ve işleçleri sahiptir.|atlcur.h|
|[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)|Bu sınıf, bir dizi depolar `IUnknown` işaretçileri.|atlcom.h|
|[CComEnum](../../atl/reference/ccomenum-class.md)|Bu sınıf, bir dizi üzerinde temel bir COM Numaralandırıcı nesnesi tanımlar.|atlcom.h|
|[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)|Bu sınıf, numaralandırılan öğeleri bir dizi içinde depolandığı bir COM Numaralandırıcı arabirimi uygulamasını sağlar.|atlcom.h|
|[CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md)|Bu sınıf, bir C++ Standart Kitaplığı koleksiyonuna bağlı bir COM Numaralandırıcı nesnesi tanımlar.|atlcom.h|
|[CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)|Bu sınıf olarak aynı yöntemler sağlar [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) ancak kritik bölüm sağlamaz.|atlcore.h|
|[Ccomgıtptr](../../atl/reference/ccomgitptr-class.md)|Bu sınıf, arabirim işaretçilerini başa çıkmak için yöntemleri ve genel arabirim tablosu (GIT) sağlar.|atlbase.h|
|[CComHeap](../../atl/reference/ccomheap-class.md)|Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) COM bellek ayırma işlevlerini kullanma.|ATLComMem.h|
|[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)|Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfının.|atlbase.h|
|[CComModule](../../atl/reference/ccommodule-class.md)|ATL 7. 0'den itibaren `CComModule` artık kullanılmıyor: bkz [ATL modülleri](../../atl/atl-module-classes.md) daha fazla ayrıntı için.|atlbase.h|
|[CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)|Bu sınıf bir değişkenin değerini artırma ve azaltma için iş parçacığı açısından güvenli yöntemleri sağlar.|atlbase.h|
|[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)|Bu sınıf kritik bölümü kilitleme veya kilidini açma işlevselliği artırma ve azaltma bir değişkenin değerini için iş parçacığı açısından güvenli yöntemleri sağlar.|atlbase.h|
|[CComObject](../../atl/reference/ccomobject-class.md)|Bu sınıfın uyguladığı `IUnknown` toplanmayan bir nesne.|atlcom.h|
|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)|Bu sınıf modül bulunduğu bir başvuru sayısını yönetir, `Base` nesne.|atlcom.h|
|[CComObjectNoLock](../../atl/reference/ccomobjectnolock-class.md)|Bu sınıfın uyguladığı `IUnknown` toplanmayan bir nesne, ancak mu modülün kilit sayacını oluşturucuda artırma.|atlcom.h|
|[CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)|Bu tür tanımı, [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) iş parçacığı modeli sunucusunun varsayılan şablonlaştırılmış.|atlcom.h|
|[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)|Bu sınıf, toplanmayan ve toplanan nesneler için nesne başvuru sayısı Yönetimi işlemek için yöntemler sağlar.|atlcom.h|
|[CComObjectStack](../../atl/reference/ccomobjectstack-class.md)|Bu sınıf, geçici bir COM nesnesi oluşturur ve ile iskelet bir uygulamasını sağlar `IUnknown`.|atlcom.h|
|[CComPolyObject](../../atl/reference/ccompolyobject-class.md)|Bu sınıfın uyguladığı `IUnknown` toplanmış veya toplanmayan bir nesne için.|atlcom.h|
|[CComPtr](../../atl/reference/ccomptr-class.md)|COM arabirim işaretçilerini yönetmek için bir akıllı işaretçi sınıfının.|atlcomcli.h|
|[CComPtrBase](../../atl/reference/ccomptrbase-class.md)|Bu sınıf, COM tabanlı bellek yordamları kullanarak akıllı işaretçi sınıflar için temel sağlar.|atlcomcli.h|
|[CComQIPtr](../../atl/reference/ccomqiptr-class.md)|COM arabirim işaretçilerini yönetmek için bir akıllı işaretçi sınıfının.|atlcomcli.h|
|[Ccomqıptrelementtraits](../../atl/reference/ccomqiptrelementtraits-class.md)|Bu sınıf, yöntem, statik işlevler ve tür tanımları yararlı COM arabirim işaretçilerini koleksiyonları oluştururken sağlar.|atlcoll.h|
|[CComSafeArray](../../atl/reference/ccomsafearray-class.md)|Bu sınıf için bir sarmalayıcı olan `SAFEARRAY Data Type` yapısı.|atlsafe.h|
|[CComSafeArrayBound](../../atl/reference/ccomsafearraybound-class.md)|Bu sınıf için bir sarmalayıcı olan bir `SAFEARRAYBOUND` yapısı.|atlsafe.h|
|[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)|Bu sınıf, sınıf için iş parçacığı seçimi yönetir [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).|atlbase.h|
|[CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md)|Bu sınıf bir değişkenin değerini artırma ve azaltma için yöntemler sağlar.|atlbase.h|
|[CComTearOffObject](../../atl/reference/ccomtearoffobject-class.md)|Bu sınıf, bir etiket arabirimini uygular.|atlcom.h|
|[CComUnkArray](../../atl/reference/ccomunkarray-class.md)|Bu sınıf depolar `IUnknown` işaretçileri ve parametre olarak kullanılmak üzere tasarlanmış [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) Şablon sınıfı.|atlcom.h|
|[CComVariant](../../atl/reference/ccomvariant-class.md)|Bu sınıf, depolanan veri türünü gösteren bir üye sağlama VARIANT türü sarmalar.|atlcomcli.h|
|[CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)|Bu sınıf, başka bir nesne içinde yer alan bir pencere uygular.|atlwin.h|
|[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)|Bu sınıf, CRT bellek yordamları kullanarak bellek yönetmek için yöntemler sağlar.|atlcore.h|
|[CCRTHeap](../../atl/reference/ccrtheap-class.md)|Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) CRT yığın işlevlerinin kullanarak.|atlmem.h|
|[CDacl](../../atl/reference/cdacl-class.md)|(İsteğe bağlı erişim denetimi listesi) DACL yapısı için bir sarmalayıcı sınıftır.|atlsecurity.h|
|[CDebugReportHook Sınıfı](../../atl/reference/cdebugreporthook-class.md)|Bu sınıf, hata ayıklama raporları bir adlandırılmış kanala göndermek için kullanın.|atlutil.h|
|[CDefaultCharTraits](../../atl/reference/cdefaultchartraits-class.md)|Bu sınıf, büyük ve küçük arasındaki karakter dönüştürme için iki statik işlevler sağlar.|atlcoll.h|
|[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)|Bu sınıf, varsayılan öğe karşılaştırma işlevleri sağlar.|atlcoll.h|
|[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)|Bu sınıf, bir koleksiyon sınıfı için varsayılan yöntemleri ve işlevleri sağlar.|atlcoll.h|
|[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)|Bu sınıf, karma değerleri hesaplamak için statik işlev sağlar.|atlcoll.h|
|[Cdialogımpl](../../atl/reference/cdialogimpl-class.md)|Bu sınıf, kalıcı veya geçici bir iletişim kutusu oluşturmak için yöntemleri sağlar.|atlwin.h|
|[CDynamicChain](../../atl/reference/cdynamicchain-class.md)|Bu sınıf ileti eşlemeleri dinamik zincirleme destekleyen yöntemler sağlar.|atlwin.h|
|[CElementTraits](../../atl/reference/celementtraits-class.md)|Bu sınıf, taşıma, kopyalama, karşılaştırma ve karma işlemleri için yöntemleri ve işlevleri sağlamak için koleksiyon sınıfları tarafından kullanılır.|atlcoll.h|
|[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)|Bu sınıf, varsayılan copy sağlar ve bir koleksiyon sınıfı yöntemleri taşıyın.|atlcoll.h|
|[CFirePropNotifyEvent](../../atl/reference/cfirepropnotifyevent-class.md)|Bu sınıfın sağladığı yöntemlerle kapsayıcının havuz denetimi özellik değişiklikleri ile ilgili bilgilendirme.|atlctl.h|
|[CGlobalHeap](../../atl/reference/cglobalheap-class.md)|Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) Win32 genel yığın işlevlerini kullanma.|atlmem.h|
|[CHandle](../../atl/reference/chandle-class.md)|Bu sınıf, oluşturma ve bir tanıtıcı nesnesi kullanılarak yöntemleri sağlar.|atlbase.h|
|[CHeapPtr](../../atl/reference/cheapptr-class.md)|Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfının.|atlcore.h|
|[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)|Bu sınıfın birkaç akıllı yığın işaretçisi sınıfları temelini oluşturur.|atlcore.h|
|[CHeapPtrElementTraits Sınıfı](../../atl/reference/cheapptrelementtraits-class.md)|Bu sınıf, yığın işaretçileri koleksiyonları oluştururken yöntemleri statik işlevler ve tür tanımları yararlı sağlar.|atlcoll.h|
|[CHeapPtrList](../../atl/reference/cheapptrlist-class.md)|Bu sınıf, yığın işaretçileri listesini oluştururken kullanışlı yöntemler sağlar.|atlcoll.h|
|[Cımage](../../atl-mfc-shared/reference/cimage-class.md)|Yük ve görüntüleri JPEG, BMP, GIF ve da Taşınabilir Ağ Grafikleri (PNG) biçimlerde kaydetme olanağı dahil olmak üzere Gelişmiş bit eşlem desteği sağlar.|atlimage.h|
|[Cınterfacearray](../../atl/reference/cinterfacearray-class.md)|Bu sınıf, bir COM arabirimi işaretçiler dizisi oluştururken kullanışlı yöntemler sağlar.|atlcoll.h|
|[Cınterfacelist](../../atl/reference/cinterfacelist-class.md)|Bu sınıf, COM arabirim işaretçilerini listesini oluştururken kullanışlı yöntemler sağlar.|atlcoll.h|
|[CLocalHeap](../../atl/reference/clocalheap-class.md)|Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) Win32 yerel yığın işlevlerini kullanma.|atlmem.h|
|[CMessageMap](../../atl/reference/cmessagemap-class.md)|Bu sınıf, başka bir nesne tarafından erişilecek bir nesnenin ileti eşlemeleri sağlar.|atlwin.h|
|[CNonStatelessWorker Sınıfı](../../atl/reference/cnonstatelessworker-class.md)|Bir iş parçacığı havuzundan isteklerini alır ve bunları her istekte oluşturulur ve imha bir alt nesnesi açın geçirir.|atlutil.h|
|[CNoWorkerThread Sınıfı](../../atl/reference/cnoworkerthread-class.md)|Bu sınıf için bağımsız değişken olarak kullanmak `MonitorClass` dinamik önbellek bakım devre dışı bırakmak istiyorsanız şablon parametresi önbelleği sınıfları.|atlutil.h|
|[CPathT Sınıfı](../../atl/reference/cpatht-class.md)|Bu sınıf, bir yol gösterir.|atlpath.h|
|[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)|Bu sınıfın sağladığı yöntemlerle varsayılan ve işlevleri koleksiyon sınıfı için temel veri türlerini oluşur.|atlcoll.h|
|[CPrivateObjectSecurityDesc](../../atl/reference/cprivateobjectsecuritydesc-class.md)|Bu sınıf, bir özel nesneye güvenli tanımlayıcısı nesnesi temsil eder.|atlsecurity.h|
|[CRBMap](../../atl/reference/crbmap-class.md)|Bu sınıf, Red-siyah bir ikili Ağacı'nı kullanarak bir eşleme yapısını temsil eder.|atlcoll.h|
|[CRBMultiMap](../../atl/reference/crbmultimap-class.md)|Bu sınıf, her anahtar Red-siyah bir ikili Ağacı'nı kullanarak birden fazla değer ile ilişkilendirilecek izin veren bir eşleme yapısını temsil eder.|atlcoll.h|
|[CRBTree](../../atl/reference/crbtree-class.md)|Bu sınıf, oluşturma ve Red-siyah ağaç kullanan yöntemleri sağlar.|atlcoll.h|
|[CRegKey](../../atl/reference/cregkey-class.md)|Bu sınıf girişleri sistem kayıt defterinde yönlendirmeye yönelik yöntemleri sağlar.|atlbase.h|
|[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)|Bu sınıf için CRT iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanacaksanız kullanın.|atlbase.h|
|[CSacl](../../atl/reference/csacl-class.md)|(Sistem erişim denetim listesi) SACL yapısı için bir sarmalayıcı sınıftır.|atlsecurity.h|
|[CSecurityAttributes](../../atl/reference/csecurityattributes-class.md)|Bu sınıf için basit bir sarmalayıcı olan `SECURITY_ATTRIBUTES` yapısı.|atlsecurity.h|
|[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)|Bu sınıf için bir sarmalayıcı olan `SECURITY_DESCRIPTOR` yapısı.|atlsecurity.h|
|[CSid](../../atl/reference/csid-class.md)|Bu sınıf için bir sarmalayıcı olan bir `SID` (güvenlik kimliği) yapısı.|atlsecurity.h|
|[CSimpleArray](../../atl/reference/csimplearray-class.md)|Bu sınıf, bir Basit dizi yönetmek için yöntemler sağlar.|atlsimpcoll.h|
|[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)|Bu sınıf için Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.|atlsimpcoll.h|
|[CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)|Bu sınıf için Yardımcısı, [CSimpleArray](../../atl/reference/csimplearray-class.md) sınıfı.|atlsimpcoll.h|
|[CSimpleDialog](../../atl/reference/csimpledialog-class.md)|Bu sınıf temel kalıcı bir iletişim kutusu uygular.|atlwin.h|
|[CSimpleMap](../../atl/reference/csimplemap-class.md)|Bu sınıf, bir basit eşleme dizisi için destek sağlar.|atlsimpcoll.h|
|[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)|Bu sınıf için Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.|atlsimpcoll.h|
|[CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)|Bu sınıf için Yardımcısı, [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfı.|atlsimpcoll.h|
|[CSnapInItemImpl](../../atl/reference/csnapinitemimpl-class.md)|Bu sınıf, bir ek düğüm nesnesi uygulamak için yöntemler sağlar.|atlsnap.h|
|[CSnapInPropertyPageImpl](../../atl/reference/csnapinpropertypageimpl-class.md)|Bu sınıf, bir ek özellik sayfa nesnesi uygulamak için yöntemler sağlar.|atlsnap.h|
|[CStockPropImpl](../../atl/reference/cstockpropimpl-class.md)|Bu sınıf, stok özellik değerleri desteklemek için yöntemler sağlar.|atlctl.h|
|[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)|Statik işlevler depolama koleksiyon sınıfları tarafından kullanılan bu sınıfın sağladığı `CString` nesneleri.|cstringt.h|
|[Cstringelementtraitsı](../../atl/reference/cstringelementtraitsi-class.md)|Bu sınıf, koleksiyon sınıfı nesnelerini içinde depolanan dizeleri ilgili statik işlevler sağlar. Benzer [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), ancak büyük küçük harf duyarsız bir karşılaştırma gerçekleştirir.|atlcoll.h|
|[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)|Bu sınıf, koleksiyon sınıfı nesnelerini içinde depolanan dizeleri ilgili statik işlevler sağlar. Dize nesnelerinin, başvuru olarak ile dağıtılır.|atlcoll.h|
|[CThreadPool Sınıfı](../../atl/reference/cthreadpool-class.md)|Bu sınıf, iş öğelerinin bir kuyruğu işleyen çalışan iş parçacığı havuzu sağlar.|atlutil.h|
|[CTokenGroups](../../atl/reference/ctokengroups-class.md)|Bu sınıf için bir sarmalayıcı olan `TOKEN_GROUPS` yapısı.|atlsecurity.h|
|[CTokenPrivileges](../../atl/reference/ctokenprivileges-class.md)|Bu sınıf için bir sarmalayıcı olan `TOKEN_PRIVILEGES` yapısı.|atlsecurity.h|
|[CUrl Sınıfı](../../atl/reference/curl-class.md)|Bu sınıf, bir URL temsil eder. Var olan bir URL Ayrıştırma olup olmadığını her öğeyi diğerlerinden URL'sinin düzenlemesini sağlar dize veya bir dize sıfırdan oluşturma.|atlutil.h|
|[CW2AEX](../../atl/reference/cw2aex-class.md)|Bu sınıf, dize dönüşüm makroları CT2AEX, CW2TEX, CW2CTEX ve CT2CAEX ve typedef CW2A tarafından kullanılır.|atlconv.h|
|[CW2CWEX](../../atl/reference/cw2cwex-class.md)|Bu sınıf, dize dönüşüm makroları CW2CTEX ve CT2CWEX ve typedef CW2CW tarafından kullanılır.|atlconv.h|
|[CW2WEX](../../atl/reference/cw2wex-class.md)|Bu sınıf, dize dönüşüm makroları CW2TEX ve CT2WEX ve typedef CW2W tarafından kullanılır.|atlconv.h|
|[CWin32Heap](../../atl/reference/cwin32heap-class.md)|Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) Win32 yığın ayırma işlevleri kullanarak.|atlmem.h|
|[CWindow](../../atl/reference/cwindow-class.md)|Bu sınıf, bir pencere yönlendirmeye yönelik yöntemleri sağlar.|atlwin.h|
|[CWindowImpl](../../atl/reference/cwindowimpl-class.md)|Bu sınıf, oluşturmak veya bir pencereyi alt sınıf yapma yöntemleri sağlar.|atlwin.h|
|[CWinTraits](../../atl/reference/cwintraits-class.md)|Bu sınıf, bir pencere nesnesi oluşturulurken kullanılan stilleri Standartlaştırma için bir yöntem sağlar.|atlwin.h|
|[CWinTraitsOR](../../atl/reference/cwintraitsor-class.md)|Bu sınıf, bir pencere nesnesi oluşturulurken kullanılan stilleri Standartlaştırma için bir yöntem sağlar.|atlwin.h|
|[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)|Bu sınıf, bir pencere sınıfının bilgileri kaydetmek için yöntemler sağlar.|atlwin.h|
|[CWorkerThread Sınıfı](../../atl/reference/cworkerthread-class.md)|Bu sınıf bir çalışan iş parçacığı oluşturur veya mevcut bir kullanır, bir veya daha fazla çekirdek nesne tutamaçları bekler ve tutamaçlarından birinin sinyal, belirtilen istemci işlevi yürütür.|atlutil.h|
|[Iatlautothreadmodule](../../atl/reference/iatlautothreadmodule-class.md)|Bu sınıf için bir arabirimi temsil eder bir `CreateInstance` yöntemi.|atlbase.h|
|[Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md)|Bu sınıf, bir bellek yöneticisi için bir arabirimi temsil eder.|atlmem.h|
|[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)|Bu arabirim, barındırılan denetim veya kapsayıcı özelliklerini belirtmek için yöntemler sağlar.|atlbase.h, ATLIFace.h|
|[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)|Bu arabirim, barındırılan bir denetim için ek ortam özelliklerine uygular.|atlbase.h, ATLIFace.h|
|[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)|Bu arabirim, Denetim ve onun ana nesneyi düzenlemek için yöntemler sağlar.|atlbase.h, ATLIFace.h|
|[IAxWinHostWindowLic](../../atl/reference/iaxwinhostwindowlic-interface.md)|Bu arabirim, lisanslı bir denetim ve onun ana nesneyi işlemek için yöntemler sağlar.|atlbase.h, ATLIFace.h|
|[Icollectiononstlımpl](../../atl/reference/icollectiononstlimpl-class.md)|Bu sınıf, bir koleksiyon sınıfı tarafından kullanılan yöntemleri sağlar.|atlcom.h|
|[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)|Bu sınıfın uyguladığı bir koleksiyonu yönetmek için bir bağlantı noktası kapsayıcı [Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) nesneleri.|atlcom.h|
|[Iconnectionpointımpl](../../atl/reference/iconnectionpointimpl-class.md)|Bu sınıf, bir bağlantı noktası uygular.|atlcom.h|
|[Idataobjectımpl](../../atl/reference/idataobjectimpl-class.md)|Bu sınıf, Tekdüzen veri aktarımı destekleyen ve bağlantıları yönetmek için yöntemler sağlar.|atlctl.h|
|[Idispatchımpl](../../atl/reference/idispatchimpl-class.md)|Bu sınıf için varsayılan bir uygulama sağlar `IDispatch` çift arabirim kısmı.|atlcom.h|
|[IDispEventImpl](../../atl/reference/idispeventimpl-class.md)|Bu sınıf uygulamalarını sağlar `IDispatch` yöntemleri.|atlcom.h|
|[IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)|Bu sınıf uygulamalarını sağlar `IDispatch` yöntemleri olmadan bir tür kitaplığından türü bilgileri alınıyor.|atlcom.h|
|[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)|Bir arabirim Microsoft HTML Ayrıştırma ve işleme altyapısı.|atlbase.h, ATLIFace.h|
|[IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)|Bu sınıf, bir C++ Standart Kitaplığı koleksiyonuna bağlı bir numaralandırıcı arabirimi tanımlar.|atlcom.h|
|[IObjectSafetyImpl](../../atl/reference/iobjectsafetyimpl-class.md)|Bu sınıfın bir varsayılan uygulamayı sağlar `IObjectSafety` almak ve bir nesnenin güvenlik düzeylerini ayarlamak bir istemci izin vermek için arabirim.|atlctl.h|
|[IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md)|Bu sınıf, siteyle iletişim için bir nesne sağlayan yöntemlerini sağlar.|atlcom.h|
|[IOleControlImpl](../../atl/reference/iolecontrolimpl-class.md)|Bu sınıfın bir varsayılan uygulamayı sağlar `IOleControl` uygular ve arabirimi `IUnknown`.|atlctl.h|
|[IOleInPlaceActiveObjectImpl](../../atl/reference/ioleinplaceactiveobjectimpl-class.md)|Bu sınıf, bir yerinde denetim kapsayıcısı arasındaki iletişimi uygulayıcılarına yardımcı yöntemleri sağlar.|atlctl.h|
|[IOleInPlaceObjectWindowlessImpl](../../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve pencere iletileri almak ve sürükle ve bırak işlemleri katılmak için penceresiz denetime olanak tanıyan yöntemler sağlar.|atlctl.h|
|[IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve kapsayıcı bir denetimle iletişim asıl arabirimidir.|atlctl.h|
|[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve bir istemci bir nesnenin özellik sayfalarındaki bilgilere erişmesine izin verir.|atlctl.h|
|[IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve bir nesne için bir istemci tarafından sağlanan özellik paketi özelliklerini kaydetmek sağlar.|atlcom.h|
|[Ipersiststorageımpl](../../atl/reference/ipersiststorageimpl-class.md)|Bu sınıfın uyguladığı [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage) arabirimi.|atlcom.h|
|[Ipersiststreamınitımpl](../../atl/reference/ipersiststreaminitimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi.|atlcom.h|
|[Ipointerınactiveımpl](../../atl/reference/ipointerinactiveimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve [Ipointerınactive'i](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) arabirim yöntemleri.|atlctl.h|
|[IPropertyNotifySinkCP](../../atl/reference/ipropertynotifysinkcp-class.md)|Bu sınıf sunan [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) arabirimi bağlanılabilirlik nesnesi üzerinde giden bir arabirim olarak.|atlctl.h|
|[Ipropertypage2ımpl](../../atl/reference/ipropertypage2impl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve varsayılan uygulamasını devralan [Ipropertypageımpl](../../atl/reference/ipropertypageimpl-class.md).|atlctl.h|
|[Ipropertypageımpl](../../atl/reference/ipropertypageimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) arabirimi.|atlctl.h|
|[IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)|Bu sınıfın bir varsayılan uygulamayı sağlar [Iprovideclassınfo](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo) ve [IProvideClassInfo2](/windows/desktop/api/ocidl/nn-ocidl-iprovideclassinfo2) yöntemleri.|atlcom.h|
|[IQuickActivateImpl](../../atl/reference/iquickactivateimpl-class.md)|Bu sınıf, kapsayıcılar denetimi başlatma tek bir çağrı halinde birleştirir.|atlctl.h|
|[IRunnableObjectImpl](../../atl/reference/irunnableobjectimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IRunnableObject](/windows/desktop/api/objidl/nn-objidl-irunnableobject) arabirimi.|atlctl.h|
|[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)|Bu sınıfın bir varsayılan uygulamayı sağlar `IServiceProvider` arabirimi.|atlcom.h|
|[Ispecifypropertypagesımpl](../../atl/reference/ispecifypropertypagesimpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [ISpecifyPropertyPages](/windows/desktop/api/ocidl/nn-ocidl-ispecifypropertypages) arabirimi.|atlcom.h|
|[Isupporterrorınfoımpl](../../atl/reference/isupporterrorinfoimpl-class.md)|Bu sınıfın bir varsayılan uygulamayı sağlar `ISupportErrorInfo Interface` arabirim ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.|atlcom.h|
|[IThreadPoolConfig Arabirimi](../../atl/reference/ithreadpoolconfig-interface.md)|Bu arabirim, iş parçacığı havuzu yapılandırmak için yöntemler sağlar.|atlutil.h|
|[Iviewobjectexımpl](../../atl/reference/iviewobjecteximpl-class.md)|Bu sınıfın uyguladığı `IUnknown` ve varsayılan uygulamalarını sağlar [IViewObject](/windows/desktop/api/oleidl/nn-oleidl-iviewobject), [IViewObject2](/windows/desktop/api/oleidl/nn-oleidl-iviewobject2), ve [IViewObjectEx](/windows/desktop/api/ocidl/nn-ocidl-iviewobjectex) arabirimleri.|atlctl.h|
|[IWorkerThreadClient Sınıfı](../../atl/reference/iworkerthreadclient-interface.md)|`IWorkerThreadClient` istemcileri tarafından uygulanan arabirimi [CWorkerThread](../../atl/reference/cworkerthread-class.md) sınıfı.|atlutil.h|
|[_U_menuorıd](../../atl/reference/u-menuorid-class.md)|Bu sınıfın sarmalayıcıları için sağladığı `CreateWindow` ve `CreateWindowEx`.|atlwin.h|
|[_U_RECT](../../atl/reference/u-rect-class.md)|Bu bağımsız değişken bağdaştırıcı sınıfı ya da tanır `RECT` işaretçiler veya başvurular açısından işaretçileri uygulanan bir işleve geçirilecek.|atlwin.h|
|[_U_strıngorıd](../../atl/reference/u-stringorid-class.md)|Bu bağımsız değişken bağdaştırıcısı sınıfı (LPCTSTRs) kaynak adları ya da kaynak kimlikleri (arayan kimliği MAKEINTRESOURCE makrosu kullanarak bir dizeye dönüştürmek gerek kalmadan bir işleve geçirilecek sınıfta) sağlar.|atlwin.h|
|[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)|Bu sınıf için bir Windows iş parçacığı oluşturma işlevi sağlar. Bu sınıf, iş parçacığı CRT işlevleri kullanmayacaksa kullanın.|atlbase.h|

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Masaüstü Bileşenleri](../../atl/atl-com-desktop-components.md)<br/>
[İşlevler](../../atl/reference/atl-functions.md)<br/>
[Global Değişkenler](../../atl/reference/atl-global-variables.md)<br/>
[Tür tanımları](../../atl/reference/atl-typedefs.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
