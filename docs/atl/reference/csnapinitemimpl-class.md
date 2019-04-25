---
title: Csnapınıtemımpl sınıfı
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
ms.openlocfilehash: 27f3e8a17a9538a72a6592177a88a9b415b1a27c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62277714"
---
# <a name="csnapinitemimpl-class"></a>Csnapınıtemımpl sınıfı

Bu sınıf, bir ek düğüm nesnesi uygulamak için yöntemler sağlar.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `CSnapInItemImpl`.

*bIsExtension*<br/>
Nesnenin ek uzantı ise TRUE; Aksi durumda FALSE.

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
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Sayfaları için ek bileşeninin özellik sayfası ekler.|
|[CSnapInItemImpl::FillData](#filldata)|Belirtilen akış eklentisini nesnesindeki bilgileri kopyalar.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Alır `RESULTDATAITEM` ek bileşenini yapısı.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Sonuç bölmesindeki tarafından kullanılan görünüm türünü belirler.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Alır `SCOPEDATAITEM` ek bileşenini yapısı.|
|[CSnapInItemImpl::Notify](#notify)|Kullanıcı tarafından gerçekleştirilen eylemlerin ve eklentinin bildirmek için konsolu tarafından çağrılır.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Ek bileşenini düğümü özellik sayfaları destekleyip desteklemediğini görmek için çağrılır.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Bir ek bileşen nesne menü ekleme bayrakları değiştirir.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Belirtilen araç çubuğu düğmesini bilgilerini ayarlar.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Bir bağlam menüsü öğesi durumunu güncelleştirir.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Belirtilen araç çubuğu düğmesini durumunu güncelleştirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Ek Bileşen Nesne adı.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows `RESULTDATAITEM` yapısı tarafından kullanılan `CSnapInItemImpl` nesne.|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows `SCOPEDATAITEM` yapısı tarafından kullanılan `CSnapInItemImpl` nesne.|

## <a name="remarks"></a>Açıklamalar

`CSnapInItemImpl` menü öğeleri ve araç çubuklarını ekleme ve uygun bir işleyici işlevi için ek düğüm için komutları iletme gibi ek olarak, ek bileşenini düğüm nesnesi için temel bir uygulamasını sağlar. Bu özellikler, birkaç farklı arabirimi kullanılarak uygulanır ve türleri eşlenir. Varsayılan uygulama doğru türetilmiş bir sınıf örneğini belirleyerek ve ardından doğru örneğine iletirken düğüm nesnesi için gönderilen bildirimleri işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsnap.h

##  <a name="addmenuitems"></a>  CSnapInItemImpl::AddMenuItems

Bu yöntem Win32 işlevini uygulayan [IExtendContextMenu::AddMenuItems](/windows/desktop/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems).

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*piCallback*<br/>
[in] İşaretçi `IContextMenuCallback` için bağlam menüsü öğeleri eklemek.

*pInsertionAllowed*<br/>
[out içinde] Tanımlayan kullanılacak Microsoft Yönetim Konsolu MMC tanımlı menü öğesi ekleme noktaları. Bu, aşağıdaki bayrakların birleşimi olabilir:

- Bağlam menüsünün üstünde CCM_INSERTIONALLOWED_TOP öğeleri eklenebilir.

- Yeni Oluştur alt menüde CCM_INSERTIONALLOWED_NEW öğeleri eklenebilir.

- Görev alt menüde CCM_INSERTIONALLOWED_TASK öğeleri eklenebilir.

- CCM_INSERTIONALLOWED_VIEW öğeleri araç Görünüm menüsü ya da sonuç bölmesi bağlam menüsü Görünüm alt eklenebilir.

*type*<br/>
[in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kapsam bölmesi bağlamının CCT_SCOPE veri nesnesi.

- Sonuç bölmesinde bağlamının CCT_RESULT veri nesnesi.

- Eklenti Yöneticisi içerik için CCT_SNAPIN_MANAGER veri nesnesi.

- CCT_UNINITIALIZED veri nesnesi, geçersiz bir türe sahip.

##  <a name="command"></a>  CSnapInItemImpl::Command

Bu yöntem Win32 işlevini uygulayan [IExtendContextMenu::Command](/windows/desktop/api/mmc/nf-mmc-iextendcontextmenu-command).

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*lCommandID*<br/>
[in] Menü öğesinin komut tanımlayıcısını belirtir.

*type*<br/>
[in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kapsam bölmesi bağlamının CCT_SCOPE veri nesnesi.

- Sonuç bölmesinde bağlamının CCT_RESULT veri nesnesi.

- Eklenti Yöneticisi içerik için CCT_SNAPIN_MANAGER veri nesnesi.

- CCT_UNINITIALIZED veri nesnesi, geçersiz bir türe sahip.

##  <a name="createpropertypages"></a>  CSnapInItemImpl::CreatePropertyPages

Bu yöntem Win32 işlevini uygulayan [IExtendPropertySheet::CreatePropertyPages](/windows/desktop/api/mmc/nn-mmc-iextendpropertysheet2).

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*lpProvider*<br/>
[in] İşaretçi `IPropertySheetCallback` arabirimi.

*Tanıtıcı*<br/>
[in] Uygun veri sınıfa MMCN_PROPERTY_CHANGE bildirim iletisini yönlendirmek için kullanılan tanıtıcı belirtir.

*pUnk*<br/>
[in] İşaretçi `IExtendPropertySheet` arabiriminde düğüm hakkında bağlam bilgisi içeren nesne.

*type*<br/>
[in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kapsam bölmesi bağlamının CCT_SCOPE veri nesnesi.

- Sonuç bölmesinde bağlamının CCT_RESULT veri nesnesi.

- Eklenti Yöneticisi içerik için CCT_SNAPIN_MANAGER veri nesnesi.

- CCT_UNINITIALIZED veri nesnesi, geçersiz bir türe sahip.

##  <a name="csnapinitemimpl"></a>  CSnapInItemImpl::CSnapInItemImpl

Oluşturur bir `CSnapInItemImpl` nesne.

```
CSnapInItemImpl();
```

##  <a name="filldata"></a>  CSnapInItemImpl::FillData

Bu işlev, öğe hakkında bilgi almak için çağrılır.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Parametreler

*cf*<br/>
[in] Biçimi (metin, zengin metin veya OLE öğeleri ile zengin metin) Pano.

*pStream*<br/>
[in] Nesne verilerini içeren akış için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev düzgün bir şekilde uygulamak için doğru bilgileri akışa kopyalayın (*pStream*) tarafından belirtilen Pano biçimi bağlı olarak *cf*.

##  <a name="getresultviewtype"></a>  CSnapInItemImpl::GetResultViewType

Sonuç bölmesini eklentisini nesnenin görünümünü türünü almak için bu işlevi çağırın.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Parametreler

*ppViewType*<br/>
[out] Adres döndürülen görünüm türünün işaretçisi.

*pViewOptions*<br/>
[out] Konsolu, sahip olan ek bileşenini tarafından belirtilen seçeneklerle sağlar MMC_VIEW_OPTIONS sabit listesi için işaretçi. Bu değer aşağıdakilerden biri olabilir:

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001 belirten standart liste görünümü seçenekleri görüntülemesini ayarladıysa konsola **görünümü** menüsü. Ek bileşeni, kendi özel görünümlerinizi yalnızca sonuç görünümü bölmesinde görüntülenecek sağlar. Şu anda tanımlı olan tek seçenek bayrak budur.

- MMC_VIEW_OPTIONS_NONE verir 0 = varsayılan görüntüleme seçenekleri.

##  <a name="getscopepaneinfo"></a>  CSnapInItemImpl::GetScopePaneInfo

Almak için bu işlevi çağırın `SCOPEDATAITEM` ek bileşenini yapısı.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Parametreler

*pScopeDataItem*<br/>
[out] Bir işaretçi `SCOPEDATAITEM` yapısını `CSnapInItemImpl` nesne.

##  <a name="getresultpaneinfo"></a>  CSnapInItemImpl::GetResultPaneInfo

Almak için bu işlevi çağırın `RESULTDATAITEM` ek bileşenini yapısı.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Parametreler

*pResultDataItem*<br/>
[out] Bir işaretçi `RESULTDATAITEM` yapısını `CSnapInItemImpl` nesne.

##  <a name="m_bstrdisplayname"></a>  CSnapInItemImpl::m_bstrDisplayName

Düğüm öğe için görüntülenen dizeyi içerir.

```
CComBSTR m_bstrDisplayName;
```

##  <a name="m_scopedataitem"></a>  CSnapInItemImpl::m_scopeDataItem

`SCOPEDATAITEM` Yapısını ek veri nesnesi.

```
SCOPEDATAITEM m_scopeDataItem;
```

##  <a name="m_resultdataitem"></a>  CSnapInItemImpl::m_resultDataItem

[RESULTDATAITEM](/windows/desktop/api/mmc/ns-mmc-resultdataitem) yapısını ek veri nesnesi.

```
RESULTDATAITEM m_resultDataItem;
```

##  <a name="notify"></a>  CSnapInItemImpl::Notify

Ek Bileşen Nesne kullanıcı tarafından izlemede çağrılır.

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
[in] Bir kullanıcı tarafından gerçekleştirilen bir eylem belirtir. Aşağıdaki bildirimler mümkündür:

- Bir pencere edilirken MMCN_ACTIVATE gönderilen etkinleştirilir ve devre dışı bırakıldı.

- Görüntüleri sonucu bölmesine eklemek için MMCN_ADD_IMAGES gönderilir.

- Kullanıcı araç çubuğu düğmeleri tıkladığında MMCN_BTN_CLICK gönderilir.

- Bir kullanıcı bir liste görünümü öğesi bir fare düğmesine tıkladığında MMCN_CLICK gönderilir.

- Bir kullanıcı bir liste görünümü öğesi bir fare düğmesine çift tıkladığında MMCN_DBLCLICK gönderilir.

- MMCN_DELETE nesne olmalıdır ve eklentinin bilgilendirmek için gönderilen silindi.

- Bir klasör ayrılmadan veya genişletilmeden sözleşmeleri yapılır gerektiğinde MMCN_EXPAND gönderilir.

- Bir pencere edilirken MMCN_MINIMIZED gönderilen küçültülebilir ya da ekranı.

- Ek bileşenini nesnenin görünümü değişmek üzere bir ek bileşenini nesnesini bildirmek için MMCN_PROPERTY_CHANGE gönderdi.

- Tüm alt ağacı ek bileşenini silmeniz gerektiğinde MMCN_REMOVE_CHILDREN gönderilen belirtilen düğümün eklemiştir.

- İlk kez sorgu için bir yeniden adlandırma ve yeniden adlandırma yapmak için ikinci kez MMCN_RENAME gönderilir.

- Kapsam ya da sonuç görünümü bölmesinde bir öğe seçildiğinde MMCN_SELECT gönderilir.

- Kapsam öğesini seçtikten veya ilk kez seçili MMCN_SHOW gönderilir.

- Bir değişiklik olduğunda ek bileşenini tüm görünümlere güncelleştirebilirsiniz MMCN_VIEW_CHANGE gönderilir.

*bağımsız değişken*<br/>
[in] Bildirim türüne göre değişir.

*param*<br/>
[in] Bildirim türüne göre değişir.

*pComponentData*<br/>
[out] Uygulayan nesne için bir işaretçi `IComponentData`. Bildirim alanından gönderilmekte olduğu değil, bu parametre null `IComponentData::Notify`.

*pComponent*<br/>
[out] Uygulayan nesne işaretçisi `IComponent`. Bildirim alanından gönderilmekte olduğu değil, bu parametre null `IComponent::Notify`.

*type*<br/>
[in] Nesne türünü belirtir. Aşağıdaki değerlerden biri olabilir:

- Kapsam bölmesi bağlamının CCT_SCOPE veri nesnesi.

- Sonuç bölmesinde bağlamının CCT_RESULT veri nesnesi.

- Eklenti Yöneticisi içerik için CCT_SNAPIN_MANAGER veri nesnesi.

- CCT_UNINITIALIZED veri nesnesi, geçersiz bir türe sahip.

##  <a name="querypagesfor"></a>  CSnapInItemImpl::QueryPagesFor

Ek bileşenini düğümü özellik sayfaları destekleyip desteklemediğini görmek için çağrılır.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

##  <a name="setmenuinsertionflags"></a>  CSnapInItemImpl::SetMenuInsertionFlags

Tarafından belirtilen menü ekleme bayrakları değiştirmek için bu işlevi çağırın *pInsertionAllowed*, ek nesne.

```
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Parametreler

*bBeforeInsertion*<br/>
[in] Bağlam menüsüne eklenen öğeler önce işlevin çağrılması gerektiğini olursa sıfır dışı; Aksi durumda 0.

*pInsertionAllowed*<br/>
[out içinde] Tanımlayan kullanılacak Microsoft Yönetim Konsolu MMC tanımlı menü öğesi ekleme noktaları. Bu, aşağıdaki bayrakların birleşimi olabilir:

- Bağlam menüsünün üstünde CCM_INSERTIONALLOWED_TOP öğeleri eklenebilir.

- Yeni Oluştur alt menüde CCM_INSERTIONALLOWED_NEW öğeleri eklenebilir.

- Görev alt menüde CCM_INSERTIONALLOWED_TASK öğeleri eklenebilir.

- CCM_INSERTIONALLOWED_VIEW öğeleri araç Görünüm menüsü ya da sonuç bölmesi bağlam menüsü Görünüm alt eklenebilir.

### <a name="remarks"></a>Açıklamalar

Bir birincil ek bileşenini geliştiriyorsanız, herhangi bir üçüncü taraf uzantı ekleyebileceğiniz menü öğelerinin türü kısıtlama bir yolu olarak ekleme bayrakların sıfırlayabilirsiniz. Örneğin, birincil ve eklentinin uzantıları kendi yeni oluştur menü öğeleri eklemesini engellemek için CCM_INSERTIONALLOWED_NEW bayrağı temizleyebilirsiniz.

BITS kümesinde yüklemeye çalışmamalısınız *pInsertionAllowed* , başlangıçta silinmesinden. Şu anda tanımlanmamış BITS değiştirmemelisiniz. Bu nedenle şu anda tanımlı BITS MMC gelecek sürümlerinde kullanabilirsiniz.

##  <a name="settoolbarbuttoninfo"></a>  CSnapInItemImpl::SetToolbarButtonInfo

Araç oluşturulmadan önce ek bileşenini nesnesinin tüm araç çubuğu düğmesi stilleri değiştirmek için bu işlevi çağırın.

```
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
[in] Ayarlanacak araç çubuğu düğmesini kimliği.

*fsState*<br/>
[in] Düğmenin durumu bayrakları. Bir veya daha fazlasını olabilir:

- Düğme TBSTYLE_CHECKED stilde ve basıldığında TBSTATE_CHECKED.

- TBSTATE_ENABLED düğmeyi, kullanıcı girişi kabul eder. Bu duruma sahip olmayan bir düğme kullanıcı girdisi kabul etmiyor ve renkte gösterilir.

- TBSTATE_HIDDEN düğmesi görünür değil ve kullanıcı girişi alamaz.

- TBSTATE_INDETERMINATE düğmesi gri.

- Düğmeye basıldığında TBSTATE_PRESSED.

- Düğme TBSTATE_WRAP bir satır sonu izler. Düğme de TBSTATE_ENABLED olması gerekir.

*fsType*<br/>
[in] Düğmenin durumu bayrakları. Bir veya daha fazlasını olabilir:

- TBSTYLE_BUTTON standart bir düğme oluşturur.

- Basılı ve değil basılı durumları her zaman arasında geçiş yapar kullanıcı bir düğme TBSTYLE_CHECK oluşturur, tıklar. Basılı durumdayken farklı arka plan rengi düğmesi vardır.

- Başka bir düğme grubundaki basılana kadar kalır bir onay düğmesine basıldığında TBSTYLE_CHECKGROUP oluşturur.

- Gruptaki başka bir düğmeye basıldığında kadar kalır bir düğmeye basıldığını TBSTYLE_GROUP oluşturur.

- TBSTYLE_SEP düğme grupları arasında küçük bir aralık sağlayan bir ayırıcı oluşturur. Bu stil bulunan bir düğme, kullanıcı girişini almaz.

##  <a name="updatemenustate"></a>  CSnapInItemImpl::UpdateMenuState

Ek Bileşen Nesne bağlam menüsüne eklenmeden önce bir menü öğesini değiştirmek için bu işlevi çağırın.

```
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
[in] Ayarlanacak menü öğesinin kimliği.

*pBuf*<br/>
[in] Güncelleştirilecek menü öğesi için bir dizeye bir işaretçi.

*bayrakları*<br/>
[in] Yeni durum bayrakları belirtir. Bu, aşağıdaki bayrakların birleşimi olabilir:

- MF_POPUP bu bağlam menüsü içine olduğunu belirtir. Menü öğeleri ekleme noktaları ve daha fazla alt menülerini kullanarak bu alt eklenebilir, `lCommandID` olarak kendi `IInsertionPointID`.

- MF_BITMAP ve MF_OWNERDRAW Bu bayraklar izin verilmez E_INVALIDARG dönüş değeri neden olur.

- MF_SEPARATOR yatay bir çizgi çizer. Yalnızca `IContextMenuProvider` MF_SEPARATOR kümesi ile menü öğesi eklemek için izin verilir.

- Menü öğesinin yanında bir onay işareti MF_CHECKED yerleştirir.

- MF_DISABLED devre dışı bırakır menü öğesi seçilemez bu nedenle, ancak bayrağı değil gri bu.

- Bu, kendi gri durumundan geri seçilemiyor MF_ENABLED menü öğesini sağlar.

- MF_GRAYED menü öğesi seçilemez bu nedenle, grileştirmesi devre dışı bırakır.

- MF_MENUBARBREAK işlevleri MF_MENUBREAK aynı bir menü çubuğu için bayrak. Bir açılan menü, alt veya kısayol menüsünden için yeni bir sütun eski sütunu dikey bir çizgiyle ayrılır.

- (Bir menü çubuğu için) yeni bir satıra MF_MENUBREAK yerleştirir öğesi veya sütun ayırıcı olmadan yeni bir sütun (için açılan menüsünden, alt veya kısayol menüsünden).

- MF_UNCHECKED yapar (varsayılan) öğesinin yanındaki onay işareti koyun değil.

Aşağıdaki gruplar bayrakların birlikte kullanılamaz:

- MF_DISABLED MF_ENABLED ve MF_GRAYED.

- MF_MENUBARBREAK ve MF_MENUBREAK.

- MF_CHECKED ve MF_UNCHECKED.

##  <a name="updatetoolbarbutton"></a>  CSnapInItemImpl::UpdateToolbarButton

Ek bileşenini nesnesinin bir araç çubuğu düğmesi gösterilmeden önce değiştirmek için bu işlevi çağırın.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Güncelleştirilecek araç çubuğu düğmesini düğmesi Kimliğini belirtir.

*fsState*<br/>
Araç çubuğu düğmesi durumunu belirtir. Ayarlamak için bu durum ise, TRUE döndürür. Bu, aşağıdaki bayrakların birleşimi olabilir:

- Etkin, düğme kullanıcı girişi kabul eder. Bu duruma sahip olmayan bir düğme kullanıcı girdisi kabul etmiyor ve renkte gösterilir.

- Düğmenin İŞARETLİ stil sahiptir ve basıldığında teslim.

- Gizli düğmesi görünür değil ve kullanıcı girişi alamaz.

- Düğme gri BELİRSİZ.

- Düğmeye basıldığında BUTTONPRESSED.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
