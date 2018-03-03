---
title: "CSnapInItemImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1355173bafcf026a7f1bfba771a7769b202c92c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl sınıfı
Bu sınıf ek bileşenini düğüm nesnesi uygulamak için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T, BOOL bIsExtension = FALSE>  
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **DOĞRU** nesne bir ek bileşeni uzantısı; ise aksi **FALSE**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Menü öğeleri için bir bağlam menüsü ekler.|  
|[CSnapInItemImpl::Command](#command)|Özel menü öğesi seçildiğinde Konsolu tarafından çağrılır.|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Sayfalar ek bileşenini, özellik sayfasına ekler.|  
|[CSnapInItemImpl::FillData](#filldata)|Belirtilen akışa ek bileşenini nesne bilgiler kopyalar.|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Alır **RESULTDATAITEM** ek bileşenini yapısı.|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Sonuç bölmesindeki tarafından kullanılan görünüm türünü belirler.|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Alır **SCOPEDATAITEM** ek bileşenini yapısı.|  
|[CSnapInItemImpl::Notify](#notify)|Ek bileşenini kullanıcı tarafından gerçekleştirilen eylemlerin bildirmek için konsolu tarafından çağrılır.|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Ek bileşenini düğüm özellik sayfaları destekleyip desteklemediğini görmek için çağrılır.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Bir ek bileşen nesne için menü ekleme bayrakları değiştirir.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Belirtilen araç çubuğu düğmesi bilgilerini ayarlar.|  
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Bir bağlam menüsü öğesini durumunu güncelleştirir.|  
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Belirtilen araç çubuğu düğmesi durumunu güncelleştirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Ek bileşenini nesnesinin adı.|  
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows **RESULTDATAITEM** tarafından kullanılan yapısı `CSnapInItemImpl` nesnesi.|  
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows **SCOPEDATAITEM** tarafından kullanılan yapısı `CSnapInItemImpl` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSnapInItemImpl`menü öğeleri ve araç çubuklarını ekleme ve komutları için uygun işleyiciyi işlevi ek düğüme iletme gibi ek olarak, ek bileşenini düğüm nesnesi için temel bir uygulama sağlar. Bu özellikler birçok farklı arabirimleri kullanılarak uygulanan ve türleri eşlenir. Varsayılan uygulama, türetilmiş sınıf doğru örneği belirleyerek ve doğru örneği iletiyi iletme düğüm nesnesi gönderilen bildirimler işler.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsnap.h  
  
##  <a name="addmenuitems"></a>CSnapInItemImpl::AddMenuItems  
 Bu yöntem Win32 işlevi uygulayan [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841).  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parametreler  
 *piCallback*  
 [in] İşaretçi **IContextMenuCallback** bağlam menüsü öğeleri eklemek.  
  
 `pInsertionAllowed`  
 [içinde out] Tanımlayan kullanılabilecek Microsoft Yönetim Konsolu MMC tanımlı menü öğesi ekleme noktaları. Bu aşağıdaki bayraklar bir bileşimi olabilir:  
  
- **CCM_INSERTIONALLOWED_TOP** öğeleri bir bağlam menüsü üstünde eklenebilir.  
  
- **CCM_INSERTIONALLOWED_NEW** Yeni Oluştur alt öğeleri eklenebilir.  
  
- **CCM_INSERTIONALLOWED_TASK** görev alt öğeleri eklenebilir.  
  
- **CCM_INSERTIONALLOWED_VIEW** araç Görünüm menüsü veya sonuç bölmesinde bağlam menüsünden görünümü alt öğeleri eklenebilir.  
  
 `type`  
 [in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **CCT_SCOPE** kapsam bölmesi bağlam için veri nesnesi.  
  
- **CCT_RESULT** Sonuç bölmesinde bağlamı için veri nesnesi.  
  
- **CCT_SNAPIN_MANAGER** Yöneticisi ek bileşenini bağlamı için veri nesnesi.  
  
- **CCT_UNINITIALIZED** veri nesnesi geçersiz bir türe sahip.  
  
##  <a name="command"></a>CSnapInItemImpl::Command  
 Bu yöntem Win32 işlevi uygulayan [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842).  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parametreler  
 *lCommandID*  
 [in] Menü öğesi komut tanımlayıcısını belirtir.  
  
 `type`  
 [in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **CCT_SCOPE** kapsam bölmesi bağlam için veri nesnesi.  
  
- **CCT_RESULT** Sonuç bölmesinde bağlamı için veri nesnesi.  
  
- **CCT_SNAPIN_MANAGER** Yöneticisi ek bileşenini bağlamı için veri nesnesi.  
  
- **CCT_UNINITIALIZED** veri nesnesi geçersiz bir türe sahip.  
  
##  <a name="createpropertypages"></a>CSnapInItemImpl::CreatePropertyPages  
 Bu yöntem Win32 işlevi uygulayan [IExtendPropertySheet::CreatePropertyPages](http://msdn.microsoft.com/library/aa814846).  
  
```
CreatePropertyPages(  
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpProvider*  
 [in] İşaretçi **IPropertySheetCallback** arabirimi.  
  
 *işleme*  
 [in] Kullanılan işleyici belirtir rota **MMCN_PROPERTY_CHANGE** uygun veri sınıfı için bildirim iletisi.  
  
 *pUnk*  
 [in] İşaretçi **IExtendPropertySheet** düğüm hakkında bağlam bilgisi içeren nesneyi arabirimde.  
  
 `type`  
 [in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **CCT_SCOPE** kapsam bölmesi bağlam için veri nesnesi.  
  
- **CCT_RESULT** Sonuç bölmesinde bağlamı için veri nesnesi.  
  
- **CCT_SNAPIN_MANAGER** Yöneticisi ek bileşenini bağlamı için veri nesnesi.  
  
- **CCT_UNINITIALIZED** veri nesnesi geçersiz bir türe sahip.  
  
##  <a name="csnapinitemimpl"></a>CSnapInItemImpl::CSnapInItemImpl  
 Oluşturan bir `CSnapInItemImpl` nesnesi.  
  
```
CSnapInItemImpl();
```  
  
##  <a name="filldata"></a>CSnapInItemImpl::FillData  
 Bu işlev, öğe hakkında bilgi almak için çağrılır.  
  
```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `cf`  
 [in] Biçimi (metin, zengin metin veya OLE öğeleri içeren zengin metin) Pano.  
  
 `pStream`  
 [in] Nesne verilerini içeren akışı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev düzgün bir şekilde uygulamak için doğru bilgileri akışa kopyalayın ( `pStream`) tarafından gösterilen Pano biçimi bağlı olarak `cf`.  
  
##  <a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType  
 Sonuç bölmesindeki ek bileşenini nesnesinin görünüm türünü almak için bu işlevini çağırın.  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>Parametreler  
 *ppViewType*  
 [out] Döndürülen görünüm türü adresine işaretçi.  
  
 *pViewOptions*  
 [out] İşaretçi **MMC_VIEW_OPTIONS** sahibi olan ek bileşenini tarafından belirtilen seçeneklerle Konsolu sağlar numaralandırması. Bu değer aşağıdakilerden biri olabilir:  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0x00000001 belirten standart liste görünümü seçenekler sunan engellemeye konsol **Görünüm** menüsü. Ek bileşeni, kendi özel görünümlerinizi yalnızca sonuç görünümü bölmesinde görüntülemek sağlar. Şu anda tanımlı olan tek seçenek bayrak budur.  
  
- **MMC_VIEW_OPTIONS_NONE** = varsayılan görünüm seçenekler 0 sağlar.  
  
##  <a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo  
 Almak için bu işlevi çağırmak **SCOPEDATAITEM** ek bileşenini yapısı.  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pScopeDataItem*  
 [out] Bir işaretçi **SCOPEDATAITEM** yapısını `CSnapInItemImpl` nesnesi.  
  
##  <a name="getresultpaneinfo"></a>CSnapInItemImpl::GetResultPaneInfo  
 Almak için bu işlevi çağırmak **RESULTDATAITEM** ek bileşenini yapısı.  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pResultDataItem*  
 [out] Bir işaretçi **RESULTDATAITEM** yapısını `CSnapInItemImpl` nesnesi.  
  
##  <a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName  
 Düğüm öğe için görüntülenen dizesini içerir.  
  
```
CComBSTR m_bstrDisplayName;
```  
  
##  <a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem  
 `SCOPEDATAITEM` Yapısı ek bileşenini veri nesnesi.  
  
```
SCOPEDATAITEM m_scopeDataItem;
```  
  
##  <a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem  
 [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165) yapısı ek bileşenini veri nesnesi.  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="notify"></a>CSnapInItemImpl::Notify  
 Ek Bileşen Nesne üzerinde kullanıcı tarafından işlem çağrılır.  
  
```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `event`  
 [in] Bir kullanıcı tarafından gerçekleştirilecek bir eylem tanımlar. Aşağıdaki bildirimler desteklenir:  
  
- **MMCN_ACTIVATE** etkinleştirilir ve devre dışı olduğundan, bir pencere gönderilir.  
  
- **MMCN_ADD_IMAGES** görüntüleri sonuç bölmesine eklemek için gönderilir.  
  
- **MMCN_BTN_CLICK** kullanıcı bir araç çubuğu düğmelerini tıklattığında gönderilir.  
  
- **MMCN_CLICK** bir kullanıcı bir liste görünümü öğesi bir fare düğmesini tıklattığında gönderilir.  
  
- **MMCN_DBLCLICK** bir kullanıcı çift liste görünümü öğesi üzerinde fare düğmesini tıklattığında gönderilir.  
  
- **MMCN_DELETE** nesne olmalıdır ek bileşenini bildirmek için gönderilen silindi.  
  
- **MMCN_EXPAND** bir klasör genişletilmiş veya sözleşme yapılan gerektiğinde gönderilir.  
  
- **MMCN_MINIMIZED** bir pencere simge durumuna küçültülmüş veya ekranı sayısıdır.  
  
- **MMCN_PROPERTY_CHANGE** değiştirilmek ek bileşenini nesnenin görünümdür ek bileşen nesne bildirmek için gönderilir.  
  
- **MMCN_REMOVE_CHILDREN** gönderilen ek bileşeninde belirtilen düğümün eklediği tüm alt ağaç silmeniz gerekir.  
  
- **MMCN_RENAME** gönderilen sorgulamak için bir yeniden adlandırma ilk ve ikinci kez yeniden adlandırma yapın.  
  
- **MMCN_SELECT** kapsam veya sonuç görünümü bölmesinde bir öğe seçildiğinde gönderilir.  
  
- **MMCN_SHOW** bir kapsam öğesi seçili ya da ilk olarak seçili gönderilir.  
  
- **MMCN_VIEW_CHANGE** gönderilen bir değişiklik olduğunda ek bileşenini tüm görünümleri güncelleştirebilirsiniz.  
  
 `arg`  
 [in] Bildirim türüne bağlıdır.  
  
 `param`  
 [in] Bildirim türüne bağlıdır.  
  
 *pComponentData*  
 [out] Uygulama nesnesi için bir işaretçi **IComponentData**. Bu parametre **NULL** bildirim alanından iletilmez değil, **IComponentData::Notify**.  
  
 *pComponent*  
 [out] Bir işaretçi uygulayan nesnenin **IComponent**. Bu parametre **NULL** bildirim alanından iletilmez değil, **IComponent::Notify**.  
  
 `type`  
 [in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **CCT_SCOPE** kapsam bölmesi bağlam için veri nesnesi.  
  
- **CCT_RESULT** Sonuç bölmesinde bağlamı için veri nesnesi.  
  
- **CCT_SNAPIN_MANAGER** Yöneticisi ek bileşenini bağlamı için veri nesnesi.  
  
- **CCT_UNINITIALIZED** veri nesnesi geçersiz bir türe sahip.  
  
##  <a name="querypagesfor"></a>CSnapInItemImpl::QueryPagesFor  
 Ek bileşenini düğüm özellik sayfaları destekleyip desteklemediğini görmek için çağrılır.  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="setmenuinsertionflags"></a>CSnapInItemImpl::SetMenuInsertionFlags  
 Tarafından belirtilen menü ekleme bayrakları değiştirmek için bu işlevi çağırmak `pInsertionAllowed`, ek bileşenini nesnesi.  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>Parametreler  
 *bBeforeInsertion*  
 [in] Bağlam menüsü öğeleri eklenmeden önce işlevi çağrılmalıdır, sıfır olmayan; Aksi takdirde 0.  
  
 `pInsertionAllowed`  
 [içinde out] Tanımlayan kullanılabilecek Microsoft Yönetim Konsolu MMC tanımlı menü öğesi ekleme noktaları. Bu aşağıdaki bayraklar bir bileşimi olabilir:  
  
- **CCM_INSERTIONALLOWED_TOP** öğeleri bir bağlam menüsü üstünde eklenebilir.  
  
- **CCM_INSERTIONALLOWED_NEW** Yeni Oluştur alt öğeleri eklenebilir.  
  
- **CCM_INSERTIONALLOWED_TASK** görev alt öğeleri eklenebilir.  
  
- **CCM_INSERTIONALLOWED_VIEW** araç Görünüm menüsü veya sonuç bölmesinde bağlam menüsünden görünümü alt öğeleri eklenebilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir birincil ek bileşenini geliştiriyorsanız, herhangi bir üçüncü taraf uzantı ekleyebilirsiniz menü öğeleri tür kısıtlama bir yolu olarak ekleme bayrakların sıfırlayabilirsiniz. Örneğin, birincil ek bileşenini temizleyebilirsiniz **CCM_INSERTIONALLOWED_NEW** kendi yeni oluştur menü öğeleri ekleme uzantılarının engellemek için bayrak.  
  
 BITS kümesinde çalışmamalıdır `pInsertionAllowed` , başlangıçta silinmesinden. MMC gelecek sürümlerinde şu anda tanımlanmamış BITS değiştirmemeniz gerekir böylece şu anda tanımlı BITS kullanabilir.  
  
##  <a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::SetToolbarButtonInfo  
 Araç çubuğu oluşturulmadan önce ek bileşenini nesnesinin tüm araç çubuğu düğmesi stilleri değiştirmek için bu işlevini çağırın.  
  
```
void SetToolbarButtonInfo(  
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Ayarlanacak araç çubuğu düğmesi kimliği.  
  
 `fsState`  
 [in] Düğmenin durumu bayrakları. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `TBSTATE_CHECKED`Düğmenin bulunduğu **TBSTYLE_CHECKED** stil ve basılı olduğundan.  
  
- `TBSTATE_ENABLED`Düğme kullanıcı girişini kabul eder. Bu duruma sahip olmayan bir düğme kullanıcı girişi kabul etmez ve renkte görüntülenir.  
  
- `TBSTATE_HIDDEN`Düğmenin görünür değil ve kullanıcı girişi alamaz.  
  
- `TBSTATE_INDETERMINATE`Düğme gri.  
  
- `TBSTATE_PRESSED`Düğmeye basıldığında.  
  
- `TBSTATE_WRAP`Satır sonu düğmesi izler. Düğme ayrıca olmalıdır `TBSTATE_ENABLED`.  
  
 *fsType*  
 [in] Düğmenin durumu bayrakları. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `TBSTYLE_BUTTON`Standart bir gönderme düğmesi oluşturur.  
  
- `TBSTYLE_CHECK`Basılı ve not basılı durumlar kullanıcı bağlantıya tıkladığında her zaman arasında geçiş yapar bir düğme oluşturur. Basılı durumdayken düğmesi farklı arka plan rengi vardır.  
  
- `TBSTYLE_CHECKGROUP`Gruptaki başka bir düğmeye basıldığında kadar basılı kalır bir onay düğmesi oluşturur.  
  
- `TBSTYLE_GROUP`Gruptaki başka bir düğmeye basıldığında kadar basılı kalır bir düğme oluşturur.  
  
- `TBSTYLE_SEP`Düğme grupları arasında küçük bir boşluk sağlayan bir ayırıcı oluşturur. Bu stilde bir düğme kullanıcı girişi almaz.  
  
##  <a name="updatemenustate"></a>CSnapInItemImpl::UpdateMenuState  
 Bağlam menüsüne ek bileşenini nesnesinin yerleştirilmeden önce bir menü öğesini değiştirmek için bu işlevini çağırın.  
  
```
void UpdateMenuState(  
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 [in] Ayarlanacak menü öğesi kimliği.  
  
 `pBuf`  
 [in] Güncelleştirilecek menü öğesi için dize için bir işaretçi.  
  
 `flags`  
 [in] Yeni durumu bayrakları belirtir. Bu aşağıdaki bayraklar bir bileşimi olabilir:  
  
- **MF_POPUP** bunun bir alt bağlam menüsü içinde olduğunu belirtir. Menü öğeleri ekleme noktaları ve daha fazla alt menüler kullanarak bu alt eklenebilir, **lCommandID** olarak kendi **IInsertionPointID**.  
  
- **MF_BITMAP** ve `MF_OWNERDRAW` Bu bayraklar izin verilmez ve içinde dönüş değeri sonuçlanacaktır `E_INVALIDARG`.  
  
- **MF_SEPARATOR** yatay bölme çizgisi çizer. Yalnızca **IContextMenuProvider** ile menü öğesi eklemek için izin verilen **MF_SEPARATOR** ayarlayın.  
  
- **MF_CHECKED** menü öğesinin yanında bir onay işareti koyar.  
  
- **MF_DISABLED** menü öğesi seçilemez, ancak bayrağı, gri değil için devre dışı bırakır.  
  
- `MF_ENABLED`Bu, gri durumundan geri seçilebilir şekilde menü öğesi sağlar.  
  
- **MF_GRAYED** seçilemez böylece grileştirmesi menü öğesini devre dışı bırakır.  
  
- **MF_MENUBARBREAK** aynı işlevleri **MF_MENUBREAK** menü çubuğu için bayrak. Bir açılır menü, alt veya kısayol menüsü için yeni bir sütun eski sütunu dikey bir çizgiyle ayrılır.  
  
- **MF_MENUBREAK** (için menü çubuğu) yeni bir satır öğesi yerleştirir veya sütunları ayırarak olmadan yeni bir sütun (için açılan menüsünden, alt veya kısayol menüsünden).  
  
- **MF_UNCHECKED** (varsayılan) öğesinin yanındaki onay işareti koyun değil.  
  
 Aşağıdaki gruplar bayrakları birlikte kullanılamaz:  
  
- **MF_DISABLED**, `MF_ENABLED`, ve **MF_GRAYED**.  
  
- **MF_MENUBARBREAK** ve **MF_MENUBREAK**.  
  
- **MF_CHECKED** ve **MF_UNCHECKED**.  
  
##  <a name="updatetoolbarbutton"></a>CSnapInItemImpl::UpdateToolbarButton  
 Gösterilmeden önce ek bileşenini nesnesinin bir araç çubuğu düğmesi değiştirmek için bu işlevini çağırın.  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>Parametreler  
 `id`  
 Güncelleştirilecek araç çubuğu düğmesi düğmesi Kimliğini belirtir.  
  
 `fsState`  
 Araç çubuğu düğmesi durumunu belirtir. Bu durum ayarlanacak ise, döndürür **doğru**. Bu aşağıdaki bayraklar bir bileşimi olabilir:  
  
- **Etkin** düğmesi kullanıcı girişini kabul eder. Bu duruma sahip olmayan bir düğme kullanıcı girişi kabul etmez ve renkte görüntülenir.  
  
- **İŞARETLİ** düğmesi bulunur **İŞARETLİ** stil ve basılı olduğundan.  
  
- **Gizli** düğmesi görünür değil ve kullanıcı girişi alamaz.  
  
- **BELİRSİZ** düğmesi gri.  
  
- **BUTTONPRESSED** düğmesine basıldığında.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
