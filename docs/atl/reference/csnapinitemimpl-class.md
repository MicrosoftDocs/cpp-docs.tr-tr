---
title: CSnapInItemImpl Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
ms.openlocfilehash: 1e4f98dabd2d27b21dbe3e197f32e27ccca9d2d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330729"
---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl Sınıfı

Bu sınıf, bir snap-in düğüm nesnesi uygulamak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `CSnapInItemImpl`türetilmiştir.

*bIsExtension*<br/>
Nesne bir snap-in uzantısı ise DOĞRU; aksi takdirde YANLIŞ.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|Bağlam menüsüne menü öğeleri ekler.|
|[CSnapInItemImpl::Komut](#command)|Özel bir menü öğesi seçildiğinde konsol tarafından çağrılır.|
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Snap-in'in özellik sayfasına sayfa ekler.|
|[CSnapInItemImpl::FillData](#filldata)|Snap-in nesnesindeki bilgileri belirli bir akışta kopyalar.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Snap-in `RESULTDATAITEM` yapısını alır.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Sonuç bölmesi tarafından kullanılan görünüm türünü belirler.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Snap-in `SCOPEDATAITEM` yapısını alır.|
|[CSnapInItemImpl::Bildir](#notify)|Kullanıcı tarafından gerçekleştirilen eylemleri snap-in bildirmek için konsol tarafından çağrılır.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Snap-in düğümünün özellik sayfalarını destekleyip desteklemedığını görmek için çağrılır.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Bir snap-in nesnesi için menü ekleme bayraklarını değiştirir.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Belirtilen araç çubuğu düğmesinin bilgilerini ayarlar.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Bağlam menüsü öğesinin durumunu güncelleştirir.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Belirtilen araç çubuğu düğmesinin durumunu güncelleştirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Snap-in nesnesinin adı.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Nesne `RESULTDATAITEM` tarafından kullanılan Windows yapısı. `CSnapInItemImpl`|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Nesne `SCOPEDATAITEM` tarafından kullanılan Windows yapısı. `CSnapInItemImpl`|

## <a name="remarks"></a>Açıklamalar

`CSnapInItemImpl`menü öğeleri ve araç çubukları ekleme ve snap-in düğümü için yönlendirme komutları gibi bir yapışma düğümü nesnesi için temel bir uygulama sağlar. Bu özellikler birkaç farklı arabirim ve eşlemi türleri kullanılarak uygulanır. Varsayılan uygulama, türemiş sınıfın doğru örneğini belirleyip sonra iletiyi doğru örneğe ileterek düğüm nesnesine gönderilen bildirimleri işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsnap.h

## <a name="csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a>CSnapInItemImpl::AddMenuItems

Bu yöntem Win32 işlevini [iExtendContextMenu uygular::AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems).

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*piCallback*<br/>
[içinde] Bağlam menüsüne `IContextMenuCallback` öğe ekleyebileceğini işaretçi.

*pInsertionİzin*<br/>
[içinde, dışarı] Kullanılabilecek Microsoft Yönetim Konsolu (MMC) tanımlı, menü öğesi ekleme noktalarını tanımlar. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- CCM_INSERTIONALLOWED_TOP Öğeler bağlam menüsünün en üstüne eklenebilir.

- CCM_INSERTIONALLOWED_NEW Öğeleri Yeni Oluştur alt menüsüne eklenebilir.

- CCM_INSERTIONALLOWED_TASK Öğeler Görev alt menüsüne eklenebilir.

- CCM_INSERTIONALLOWED_VIEW Öğeler araç çubuğu görünüm menüsüne veya sonuç bölmesi bağlam menüsünün Görünüm alt menüsüne eklenebilir.

*Türü*<br/>
[içinde] Nesnetürünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- CCT_SNAPIN_MANAGER Yönetici bağlamı için veri nesnesi.

- CCT_UNINITIALIZED Veri nesnesinin geçersiz bir türü vardır.

## <a name="csnapinitemimplcommand"></a><a name="command"></a>CSnapInItemImpl::Komut

Bu yöntem Win32 işlevini [iExtendContextMenu uygular::Komut](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command).

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*lCommandID*<br/>
[içinde] Menü öğesinin komut tanımlayıcısını belirtir.

*Türü*<br/>
[içinde] Nesnetürünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- CCT_SNAPIN_MANAGER Yönetici bağlamı için veri nesnesi.

- CCT_UNINITIALIZED Veri nesnesinin geçersiz bir türü vardır.

## <a name="csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a>CSnapInItemImpl::CreatePropertyPages

Bu yöntem Win32 işlevini [iExtendPropertySheet uygular::CreatePropertyPages](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2).

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*lpSağlayıcı*<br/>
[içinde] `IPropertySheetCallback` Arabirimi işaretçi.

*Işlemek*<br/>
[içinde] bildirim iletisini MMCN_PROPERTY_CHANGE uygun veri sınıfına yönlendirmek için kullanılan tanıtıcıyı belirtir.

*Punk*<br/>
[içinde] Düğüm hakkında `IExtendPropertySheet` bağlam bilgileri içeren nesneüzerinde arabirimi işaretçi.

*Türü*<br/>
[içinde] Nesnetürünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- CCT_SNAPIN_MANAGER Yönetici bağlamı için veri nesnesi.

- CCT_UNINITIALIZED Veri nesnesinin geçersiz bir türü vardır.

## <a name="csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a>CSnapInItemImpl::CSnapInItemImpl

Bir `CSnapInItemImpl` nesne inşa eder.

```
CSnapInItemImpl();
```

## <a name="csnapinitemimplfilldata"></a><a name="filldata"></a>CSnapInItemImpl::FillData

Bu işlev, öğe hakkında bilgi almak için çağrılır.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Parametreler

*Cf*<br/>
[içinde] Pano'nun biçimi (metin, zengin metin veya OLE öğelerine sahip zengin metin).

*pStream*<br/>
[içinde] Nesne verilerini içeren akış için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi düzgün bir şekilde uygulamak için, *cf*tarafından belirtilen Pano biçimine bağlı olarak doğru bilgileri akışa *(pStream)* kopyalayın.

## <a name="csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType

Snap-in nesnesinin sonuç bölmesi için görünüm türünü almak için bu işlevi arayın.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Parametreler

*ppViewType*<br/>
[çıkış] Döndürülen görünüm türünün adresini işaretçi.

*pViewOptions*<br/>
[çıkış] Konsola snap-in sahibi tarafından belirtilen seçenekleri sağlayan numaralandırmaMMC_VIEW_OPTIONS işaretçisi. Bu değer aşağıdakilerden biri olabilir:

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 **Konsola Görünüm** menüsünde standart liste görünümü seçenekleri sunmaktan kaçınmasını söyler. Snap-in'in yalnızca sonuç görünümü bölmesinde kendi özel görünümlerini görüntülemesine olanak tanır. Bu, şu anda tanımlanan tek seçenek bayrağıdır.

- MMC_VIEW_OPTIONS_NONE = 0 Varsayılan görünüm seçeneklerine izin verir.

## <a name="csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo

Snap-in `SCOPEDATAITEM` yapısını almak için bu işlevi arayın.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Parametreler

*pScopeDataItem*<br/>
[çıkış] Nesnenin yapısına bir `SCOPEDATAITEM` işaretçi. `CSnapInItemImpl`

## <a name="csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a>CSnapInItemImpl::GetResultPaneInfo

Snap-in `RESULTDATAITEM` yapısını almak için bu işlevi arayın.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Parametreler

*pResultDataItem*<br/>
[çıkış] Nesnenin yapısına bir `RESULTDATAITEM` işaretçi. `CSnapInItemImpl`

## <a name="csnapinitemimplm_bstrdisplayname"></a><a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName

Düğüm öğesi için görüntülenen dizeiçerir.

```
CComBSTR m_bstrDisplayName;
```

## <a name="csnapinitemimplm_scopedataitem"></a><a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem

Snap-in veri nesnesinin `SCOPEDATAITEM` yapısı.

```
SCOPEDATAITEM m_scopeDataItem;
```

## <a name="csnapinitemimplm_resultdataitem"></a><a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem

Snap-in veri nesnesinin [RESULTDATAITEM](/windows/win32/api/mmc/ns-mmc-resultdataitem) yapısı.

```
RESULTDATAITEM m_resultDataItem;
```

## <a name="csnapinitemimplnotify"></a><a name="notify"></a>CSnapInItemImpl::Bildir

Snap-in nesnesi kullanıcı tarafından hareket edildiğinde çağrılır.

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

*event*<br/>
[içinde] Bir kullanıcı tarafından gerçekleştirilen bir eylemi tanımlar. Aşağıdaki bildirimler mümkündür:

- MMCN_ACTIVATE Bir pencere etkinleştirilirken ve devre dışı bırakılırken gönderilir.

- MMCN_ADD_IMAGES Sonuç bölmesine resim eklemek için gönderildi.

- kullanıcı araç çubuğu düğmelerinden birini tıklattığında gönderilen MMCN_BTN_CLICK gönderilir.

- MMCN_CLICK Bir kullanıcı liste görünümü öğesinde fare düğmesini tıklattığında gönderilir.

- MMCN_DBLCLICK Bir kullanıcı liste görünümü öğesindeki fare düğmesini çift tıkladığında gönderilir.

- MMCN_DELETE Nesnenin silinmesi gerektiğini snap-in bildirmek için gönderildi.

- MMCN_EXPAND Bir klasörün genişletilmesi veya sözleşmeyapılması gerektiğinde gönderilir.

- MMCN_MINIMIZED Bir pencere en aza indirilirken veya en üst düzeye çıkarKen gönderilir.

- MMCN_PROPERTY_CHANGE Snap-in nesnesinin görünümünün değişmek üzere olduğunu bildiren bir geri dönüş nesnesi için gönderildi.

- MMCN_REMOVE_CHILDREN Snap-in belirtilen düğümün altına eklediği alt ağacın tamamını silmek zorunda kaldığında gönderilir.

- MMCN_RENAME Yeniden adlandırma için sorgu lamak için ilk kez ve yeniden adlandırma yapmak için ikinci kez gönderdi.

- MMCN_SELECT Kapsam veya sonuç görünümü bölmesinde bir öğe seçildiğinde gönderilir.

- MMCN_SHOW Kapsam öğesi ilk kez seçildiğinde veya seçildiğinde gönderilir.

- MMCN_VIEW_CHANGE Bir değişiklik olduğunda tüm görünümleri güncelleştirebildiği zaman gönderilen.

*Arg*<br/>
[içinde] Bildirim türüne bağlıdır.

*param*<br/>
[içinde] Bildirim türüne bağlıdır.

*pComponentData*<br/>
[çıkış] Nesneye bir işaretçi `IComponentData`uygulayarak. Bildirim ' den ilatılıyorsa `IComponentData::Notify`bu parametre NULL' dur

*pBileşeni*<br/>
[çıkış] Uygulayan nesneye işaretçi. `IComponent` Bildirim ' den ilatılıyorsa `IComponent::Notify`bu parametre NULL' dur

*Türü*<br/>
[içinde] Nesnetürünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- CCT_SNAPIN_MANAGER Yönetici bağlamı için veri nesnesi.

- CCT_UNINITIALIZED Veri nesnesinin geçersiz bir türü vardır.

## <a name="csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a>CSnapInItemImpl::QueryPagesFor

Snap-in düğümünün özellik sayfalarını destekleyip desteklemedığını görmek için çağrılır.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

## <a name="csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a>CSnapInItemImpl::SetMenuInsertionFlags

Bu işlevi, *pInsertionAllowed*tarafından belirlenen menü ekleme bayraklarını değiştirmek için çağırın, içeri gir nesnesi için.

```
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Parametreler

*bBefore Ekleme*<br/>
[içinde] Öğeler bağlam menüsüne eklenmeden önce işlev çağrılması gerekiyorsa sıfır olmayan; aksi takdirde 0.

*pInsertionİzin*<br/>
[içinde, dışarı] Kullanılabilecek Microsoft Yönetim Konsolu (MMC) tanımlı, menü öğesi ekleme noktalarını tanımlar. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- CCM_INSERTIONALLOWED_TOP Öğeler bağlam menüsünün en üstüne eklenebilir.

- CCM_INSERTIONALLOWED_NEW Öğeleri Yeni Oluştur alt menüsüne eklenebilir.

- CCM_INSERTIONALLOWED_TASK Öğeler Görev alt menüsüne eklenebilir.

- CCM_INSERTIONALLOWED_VIEW Öğeler araç çubuğu görünüm menüsüne veya sonuç bölmesi bağlam menüsünün Görünüm alt menüsüne eklenebilir.

### <a name="remarks"></a>Açıklamalar

Birincil bir snap-in geliştiriyorsanız, bir üçüncü taraf uzantısı ekleyebilir menü öğeleri türünü kısıtlamak için bir yol olarak ekleme bayraklarından herhangi birini sıfırlayabilirsiniz. Örneğin, birincil snap-in uzantıları kendi Yeni Menü öğeleri oluşturmasını önlemek için CCM_INSERTIONALLOWED_NEW bayrağı nı temizleyebilirsiniz.

Başlangıçta temizlenmiş *olan pInsertionAllowed'de* bitleri ayarlamaya çalışmamalısınız. MMC'nin gelecekteki sürümleri şu anda tanımlanmamış bitleri kullanmamanız için şu anda tanımlanmamış bitler kullanabilir.

## <a name="csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::SetToolbarButtonInfo

Araç çubuğu oluşturulmadan önce, snap-in nesnesinin herhangi bir araç çubuğu düğmesi stillerini değiştirmek için bu işlevi arayın.

```
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Ayarlanacak araç çubuğu düğmesinin kimliği.

*fsState*<br/>
[içinde] Düğmenin durum bayrakları. Aşağıdakilerden biri veya birkaçı olabilir:

- TBSTATE_CHECKED Düğme TBSTYLE_CHECKED stiline sahiptir ve düğmeye basılmaktadır.

- TBSTATE_ENABLED Düğme kullanıcı girişini kabul eder. Bu duruma sahip olmayan bir düğme kullanıcı girişini kabul etmez ve gri renktedir.

- TBSTATE_HIDDEN Düğme görünmez ve kullanıcı girişi alamaz.

- TBSTATE_INDETERMINATE Düğme gri renktedir.

- TBSTATE_PRESSED Düğmeye basılıyor.

- TBSTATE_WRAP Satır sonu düğmeyi izler. Düğmede de TBSTATE_ENABLED olmalıdır.

*fsType*<br/>
[içinde] Düğmenin durum bayrakları. Aşağıdakilerden biri veya birkaçı olabilir:

- TBSTYLE_BUTTON Standart bir düğme oluşturur.

- TBSTYLE_CHECK Kullanıcı her tıkladığında basıldığında ve basılamayan durumlar arasında geçiş yapan bir düğme oluşturur. Düğmeye basıldığında farklı bir arka plan rengi vardır.

- TBSTYLE_CHECKGROUP Gruptaki başka bir düğmeye basıldığında basılı kalan bir onay düğmesi oluşturur.

- TBSTYLE_GROUP Gruptaki başka bir düğmeye basıldığında basılı kalana kadar basılı kalan bir düğme oluşturur.

- TBSTYLE_SEP Düğme grupları arasında küçük bir boşluk sağlayan bir ayırıcı oluşturur. Bu stili içeren bir düğme kullanıcı girişi almaz.

## <a name="csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a>CSnapInItemImpl::UpdateMenuState

Bir menü öğesini, içeri girme nesnesinin bağlam menüsüne eklenmeden önce değiştirmek için bu işlevi arayın.

```
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] Ayarlanacak menü öğesinin kimliği.

*pBuf*<br/>
[içinde] Menü öğesinin güncelleştirilmesi için dize için bir işaretçi.

*bayraklar*<br/>
[içinde] Yeni durum bayraklarını belirtir. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- MF_POPUP Bunun bağlam menüsünde bir alt menü olduğunu belirtir. Menü öğeleri, ekleme noktaları ve diğer alt menüler kendi olarak onun `lCommandID` `IInsertionPointID`kullanılarak bu alt menüye eklenebilir.

- MF_BITMAP ve MF_OWNERDRAW Bu bayraklar izin verilmez ve E_INVALIDARG bir dönüş değeri neden olur.

- MF_SEPARATOR Yatay bir bölme çizgisi çizer. Yalnızca `IContextMenuProvider` MF_SEPARATOR ayarlanmış menü öğeleri eklemesine izin verilir.

- MF_CHECKED Menü öğesinin yanına bir onay işareti yerleştirir.

- MF_DISABLED menü öğesini devre dışı kalamaz, böylece seçilemez, ancak bayrak onu griye göstermez.

- MF_ENABLED Menü öğesini seçilebilmesini sağlayarak gri durumuna geri döndürebilir.

- MF_GRAYED menü öğesini devre dışı kılabilir, böylece seçilemez.

- MF_MENUBARBREAK Bir menü çubuğunun MF_MENUBREAK bayrağıyla aynı işlev görür. Açılan menü, alt menü veya kısayol menüsü için yeni sütun eski sütundan dikey bir çizgiyle ayrılır.

- MF_MENUBREAK Öğeyi sütunları ayırmadan yeni bir satıra (menü çubuğu için) veya yeni bir sütuna (açılır menü, alt menü veya kısayol menüsü için) yerleştirir.

- MF_UNCHECKED Maddenin yanına onay işareti (varsayılan) yerleştirmez.

Aşağıdaki bayrak grupları birlikte kullanılamaz:

- MF_DISABLED, MF_ENABLED ve MF_GRAYED.

- MF_MENUBARBREAK ve MF_MENUBREAK.

- MF_CHECKED ve MF_UNCHECKED.

## <a name="csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a>CSnapInItemImpl::UpdateToolbarButton

Görüntülenmeden önce, içeri girme nesnesinin araç çubuğu düğmesini değiştirmek için bu işlevi arayın.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
Güncellenecek araç çubuğu düğmesinin düğme kimliğini belirtir.

*fsState*<br/>
Araç çubuğu düğmesi durumunu belirtir. Bu durum ayarlanacaksa, TRUE döndürün. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- Etkİlİ Düğme kullanıcı girişini kabul eder. Bu duruma sahip olmayan bir düğme kullanıcı girişini kabul etmez ve gri renktedir.

- KONTROL EDİlDİ Düğme KONTROL EDİlMİş stiline sahiptir ve basılmaktadır.

- GİzLİ Düğme görünmez ve kullanıcı girişi alamaz.

- BELIRSIZ düğme gri renktedir.

- BUTTONPRESSED Düğmeye basılıyor.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
