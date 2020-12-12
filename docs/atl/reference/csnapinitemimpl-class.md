---
description: 'Daha fazla bilgi edinin: Csnapınitemımpl sınıfı'
title: Csnapınitemımpl sınıfı
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
ms.openlocfilehash: c1c63f5b60d57743087bffde214d9b8addef5b8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140562"
---
# <a name="csnapinitemimpl-class"></a>Csnapınitemımpl sınıfı

Bu sınıf, bir ek bileşen düğüm nesnesi uygulamak için yöntemler sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `CSnapInItemImpl` .

*Iki kez Ifade*<br/>
Nesne bir ek bileşen uzantısı ise doğru; Aksi halde yanlış.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csnapınitemımpl:: Csnapınitemımpl](#csnapinitemimpl)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Csnapınitemımpl:: AddMenuItems](#addmenuitems)|Bağlam menüsüne menü öğeleri ekler.|
|[Csnapınitemımpl:: komutu](#command)|Özel bir menü öğesi seçildiğinde konsol tarafından çağırılır.|
|[Csnapınitemımpl:: CreatePropertyPages](#createpropertypages)|Ek bileşenin Özellik sayfasına sayfa ekler.|
|[Csnapınitemımpl:: FillData](#filldata)|Ek bileşen nesnesindeki bilgileri belirtilen akışa kopyalar.|
|[Csnapınitemımpl:: Getresultbölmesi bilgileri](#getresultpaneinfo)|`RESULTDATAITEM`Ek bileşenin yapısını alır.|
|[Csnapınitemımpl:: GetResultViewType](#getresultviewtype)|Sonuç bölmesi tarafından kullanılan görünüm türünü belirler.|
|[Csnapınitemımpl:: Getscopebölmesi bilgileri](#getscopepaneinfo)|`SCOPEDATAITEM`Ek bileşenin yapısını alır.|
|[Csnapınitemımpl:: Notify](#notify)|Kullanıcı tarafından gerçekleştirilen eylemlerin ek bileşenlerine bildirimde bulunulmayı sağlamak için konsol tarafından çağırılır.|
|[Csnapınitemımpl:: QueryPagesFor](#querypagesfor)|Ek bileşen düğümünün özellik sayfalarını destekleyip desteklemediğini görmek için çağırılır.|
|[Csnapınitemımpl:: Setmenuınsertionflags](#setmenuinsertionflags)|Bir ek bileşen nesnesi için menü ekleme bayraklarını değiştirir.|
|[Csnapınitemımpl:: Settoolbarbuttonınfo](#settoolbarbuttoninfo)|Belirtilen araç çubuğu düğmesinin bilgilerini ayarlar.|
|[Csnapınitemımpl:: UpdateMenuState](#updatemenustate)|Bir bağlam menüsü öğesinin durumunu güncelleştirir.|
|[Csnapınitemımpl:: UpdateToolbarButton](#updatetoolbarbutton)|Belirtilen araç çubuğu düğmesinin durumunu güncelleştirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Csnapınitemımpl:: m_bstrDisplayName](#m_bstrdisplayname)|Ek bileşen nesnesinin adı.|
|[Csnapınitemımpl:: m_resultDataItem](#m_resultdataitem)|`RESULTDATAITEM`Nesnesi tarafından kullanılan Windows yapısı `CSnapInItemImpl` .|
|[Csnapınitemımpl:: m_scopeDataItem](#m_scopedataitem)|`SCOPEDATAITEM`Nesnesi tarafından kullanılan Windows yapısı `CSnapInItemImpl` .|

## <a name="remarks"></a>Açıklamalar

`CSnapInItemImpl` menü öğelerini ve araç çubuklarını ekleme ve ek bileşen düğümü için komutları uygun işleyici işlevine iletme gibi bir ek bileşen düğüm nesnesi için temel bir uygulama sağlar. Bu özellikler birçok farklı arabirim ve eşleme türü kullanılarak uygulanır. Varsayılan uygulama, türetilmiş sınıfın doğru örneğini belirleyerek ve sonra iletiyi doğru örneğe ileterek düğüm nesnesine gönderilen bildirimleri işler.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsnap. h

## <a name="csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a> Csnapınitemımpl:: AddMenuItems

Bu yöntem, [IExtendContextMenu:: AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems)Win32 işlevini uygular.

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*piCallback*<br/>
'ndaki `IContextMenuCallback` Bağlam menüsüne öğe ekleyebilirler öğesine yönelik işaretçi.

*pInsertionAllowed*<br/>
[in, out] Kullanılabilecek Microsoft Yönetim Konsolu (MMC) tanımlı, menü öğesi ekleme noktalarını tanımlar. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- CCM_INSERTIONALLOWED_TOP öğeler, bağlam menüsünün üst kısmına eklenebilir.

- CCM_INSERTIONALLOWED_NEW öğeleri yeni oluştur alt menüsünde eklenebilir.

- CCM_INSERTIONALLOWED_TASK öğeler görev alt menüsüne eklenebilir.

- CCM_INSERTIONALLOWED_VIEW öğeler araç çubuğu Görünüm menüsüne veya sonuç bölmesi bağlam menüsünün görünüm alt menüsüne eklenebilir.

*türüyle*<br/>
'ndaki Nesne türünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- Kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- Sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- Ek Bileşen Yöneticisi bağlamı için veri nesnesi CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED veri nesnesinin türü geçersiz.

## <a name="csnapinitemimplcommand"></a><a name="command"></a> Csnapınitemımpl:: komutu

Bu yöntem, [IExtendContextMenu:: komutunu](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command)Win32 işlevini uygular.

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*lCommandID*<br/>
'ndaki Menü öğesinin komut tanımlayıcısını belirtir.

*türüyle*<br/>
'ndaki Nesne türünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- Kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- Sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- Ek Bileşen Yöneticisi bağlamı için veri nesnesi CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED veri nesnesinin türü geçersiz.

## <a name="csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a> Csnapınitemımpl:: CreatePropertyPages

Bu yöntem, [IExtendPropertySheet:: CreatePropertyPages](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2)Win32 işlevini uygular.

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Parametreler

*lpProvider*<br/>
'ndaki `IPropertySheetCallback` Arabirim işaretçisi.

*tutamaçlardan*<br/>
'ndaki MMCN_PROPERTY_CHANGE bildirim iletisini uygun veri sınıfına yönlendirmek için kullanılan tanıtıcıyı belirtir.

*pUnk dili*<br/>
'ndaki `IExtendPropertySheet` Nesne üzerinde, düğüm hakkındaki bağlam bilgilerini içeren arabirime yönelik işaretçi.

*türüyle*<br/>
'ndaki Nesne türünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- Kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- Sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- Ek Bileşen Yöneticisi bağlamı için veri nesnesi CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED veri nesnesinin türü geçersiz.

## <a name="csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a> Csnapınitemımpl:: Csnapınitemımpl

Bir `CSnapInItemImpl` nesnesi oluşturur.

```
CSnapInItemImpl();
```

## <a name="csnapinitemimplfilldata"></a><a name="filldata"></a> Csnapınitemımpl:: FillData

Bu işlev, öğe hakkında bilgi almak için çağrılır.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Parametreler

*CF*<br/>
'ndaki Panonun biçimi (metin, zengin metin veya OLE öğeleriyle zengin metin).

*pStream*<br/>
'ndaki Nesne verilerini içeren akışa yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlevi düzgün şekilde uygulamak için, *CF* tarafından belirtilen Pano biçimine bağlı olarak doğru bilgileri akışa (*pStream*) kopyalayın.

## <a name="csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a> Csnapınitemımpl:: GetResultViewType

Ek bileşen nesnesinin sonuç bölmesinin görünüm türünü almak için bu işlevi çağırın.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Parametreler

*ppViewType*<br/>
dışı Döndürülen görünüm türünün adresi işaretçisi.

*pViewOptions*<br/>
dışı Konsola sahip olan ek bileşen tarafından belirtilen seçenekleri sağlayan MMC_VIEW_OPTIONS numaralandırması işaretçisi. Bu değer aşağıdakilerden biri olabilir:

- MMC_VIEW_OPTIONS_NOLISTVIEWS = 0x00000001, konsola **Görünüm** menüsünde standart liste görünümü seçenekleri sunmaktan kaçınmasını söyler. Ek bileşenin kendi özel görünümlerini yalnızca sonuç görünümü bölmesinde görüntülemesini sağlar. Bu, şu anda tanımlanan tek seçenek bayrağıdır.

- MMC_VIEW_OPTIONS_NONE = 0 varsayılan görünüm seçeneklerine Izin verir.

## <a name="csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a> Csnapınitemımpl:: Getscopebölmesi bilgileri

Ek bileşenin yapısını almak için bu işlevi çağırın `SCOPEDATAITEM` .

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Parametreler

*Pscopedataıtem*<br/>
dışı Nesnenin yapısına yönelik bir işaretçi `SCOPEDATAITEM` `CSnapInItemImpl` .

## <a name="csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a> Csnapınitemımpl:: Getresultbölmesi bilgileri

Ek bileşenin yapısını almak için bu işlevi çağırın `RESULTDATAITEM` .

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Parametreler

*pResultDataItem*<br/>
dışı Nesnenin yapısına yönelik bir işaretçi `RESULTDATAITEM` `CSnapInItemImpl` .

## <a name="csnapinitemimplm_bstrdisplayname"></a><a name="m_bstrdisplayname"></a> Csnapınitemımpl:: m_bstrDisplayName

Düğüm öğesi için görünen dizeyi içerir.

```
CComBSTR m_bstrDisplayName;
```

## <a name="csnapinitemimplm_scopedataitem"></a><a name="m_scopedataitem"></a> Csnapınitemımpl:: m_scopeDataItem

`SCOPEDATAITEM`Ek bileşen veri nesnesinin yapısı.

```
SCOPEDATAITEM m_scopeDataItem;
```

## <a name="csnapinitemimplm_resultdataitem"></a><a name="m_resultdataitem"></a> Csnapınitemımpl:: m_resultDataItem

Ek bileşen veri nesnesinin [RESULTDATAITEM](/windows/win32/api/mmc/ns-mmc-resultdataitem) yapısı.

```
RESULTDATAITEM m_resultDataItem;
```

## <a name="csnapinitemimplnotify"></a><a name="notify"></a> Csnapınitemımpl:: Notify

Ek bileşen nesnesi Kullanıcı tarafından üzerinde işlem yapıldığında çağırılır.

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

*olay*<br/>
'ndaki Bir kullanıcı tarafından gerçekleştirilen eylemi tanımlar. Aşağıdaki bildirimler mümkündür:

- MMCN_ACTIVATE, bir pencere etkinleştirildiğinde ve devre dışı bırakıldığında gönderilir.

- Sonuç bölmesine görüntü eklemek için MMCN_ADD_IMAGES gönderildi.

- MMCN_BTN_CLICK, Kullanıcı araç çubuğu düğmelerinden birine tıkladığında gönderilir.

- MMCN_CLICK, Kullanıcı liste görünümü öğesinde fare düğmesine tıkladığında gönderilir.

- MMCN_DBLCLICK, Kullanıcı liste görünümü öğesinde fare düğmesine çift tıkladığında gönderilir.

- MMCN_DELETE, ek bileşene nesnenin silinmesi gerektiğini bildirmek için gönderilir.

- MMCN_EXPAND, bir klasörün genişletilmesi veya sağlaması gerektiğinde gönderilir.

- Bir pencere küçültüldüğünde veya ekranı kaplamakta olduğunda MMCN_MINIMIZED gönderilir.

- Ek bileşen nesnesinin görünümünün değiştirmek üzere olduğu bir ek bileşen nesnesine bildirmek için MMCN_PROPERTY_CHANGE gönderilir.

- Ek bileşenin, belirtilen düğümün altına eklediği tüm alt ağacı silmesi gerektiğinde MMCN_REMOVE_CHILDREN gönderilir.

- MMCN_RENAME yeniden adlandırma sorgusunun ilk kez ve yeniden adlandırma için ikinci kez gönderilmesi.

- Kapsam veya sonuç görünümü bölmesindeki bir öğe seçildiğinde MMCN_SELECT gönderilir.

- Kapsam öğesi seçildiğinde veya ilk kez seçili değilken MMCN_SHOW gönderilir.

- Ek bileşen bir değişiklik gerçekleştiğinde tüm görünümleri güncelleştiremediğinde, MMCN_VIEW_CHANGE gönderilir.

*değişkeni*<br/>
'ndaki Bildirim türüne bağlıdır.

*larına*<br/>
'ndaki Bildirim türüne bağlıdır.

*pComponentData*<br/>
dışı Uygulayan nesneye yönelik bir işaretçi `IComponentData` . Bildirimin iletilemediği Bu parametre NULL `IComponentData::Notify` .

*pComponent*<br/>
dışı Uygulayan nesneye yönelik bir işaretçi `IComponent` . Bildirimin iletilemediği Bu parametre NULL `IComponent::Notify` .

*türüyle*<br/>
'ndaki Nesne türünü belirtir. Aşağıdaki değerlerden birine sahip olabilir:

- Kapsam bölmesi bağlamı için veri nesnesi CCT_SCOPE.

- Sonuç bölmesi bağlamı için veri nesnesi CCT_RESULT.

- Ek Bileşen Yöneticisi bağlamı için veri nesnesi CCT_SNAPIN_MANAGER.

- CCT_UNINITIALIZED veri nesnesinin türü geçersiz.

## <a name="csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a> Csnapınitemımpl:: QueryPagesFor

Ek bileşen düğümünün özellik sayfalarını destekleyip desteklemediğini görmek için çağırılır.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

## <a name="csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a> Csnapınitemımpl:: Setmenuınsertionflags

Ek bileşen nesnesi için, *pInsertionAllowed* tarafından belirtilen menü ekleme bayraklarını değiştirmek için bu işlevi çağırın.

```cpp
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Parametreler

*Bbeforeekleme*<br/>
'ndaki Öğe bağlam menüsüne eklenmeden önce işlev çağrılmalıdır. Aksi takdirde 0.

*pInsertionAllowed*<br/>
[in, out] Kullanılabilecek Microsoft Yönetim Konsolu (MMC) tanımlı, menü öğesi ekleme noktalarını tanımlar. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- CCM_INSERTIONALLOWED_TOP öğeler, bağlam menüsünün üst kısmına eklenebilir.

- CCM_INSERTIONALLOWED_NEW öğeleri yeni oluştur alt menüsünde eklenebilir.

- CCM_INSERTIONALLOWED_TASK öğeler görev alt menüsüne eklenebilir.

- CCM_INSERTIONALLOWED_VIEW öğeler araç çubuğu Görünüm menüsüne veya sonuç bölmesi bağlam menüsünün görünüm alt menüsüne eklenebilir.

### <a name="remarks"></a>Açıklamalar

Birincil ek bileşen geliştiriyorsanız, bir üçüncü taraf uzantısının ekleyebilen menü öğelerinin türünü kısıtlayan bir yöntem olarak ekleme bayraklarını sıfırlayabilirsiniz. Örneğin, birincil ek bileşen, uzantılarının kendi yeni oluştur menü öğelerini eklemesini engellemek için CCM_INSERTIONALLOWED_NEW bayrağını temizleyebilir.

İlk olarak temizlenmiş *pInsertionAllowed* içindeki bitleri ayarlamaya çalışmayın. MMC 'nin gelecek sürümleri, şu anda tanımlı olmayan bitleri kullanmamalıdır. bu nedenle, şu anda tanımlanmamış bitleri değiştirmemelisiniz.

## <a name="csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a> Csnapınitemımpl:: Settoolbarbuttonınfo

Araç çubuğu oluşturulmadan önce, ek bileşen nesnesinin herhangi bir araç çubuğu düğme stilini değiştirmek için bu işlevi çağırın.

```cpp
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Ayarlanacak araç çubuğu düğmesinin KIMLIĞI.

*fsState*<br/>
'ndaki Düğmenin durum bayrakları. Aşağıdakilerden biri veya daha fazlası olabilir:

- TBSTATE_CHECKED TBSTYLE_CHECKED stiline sahiptir ve bu düğme basılabilir.

- Düğme Kullanıcı girişini kabul eder TBSTATE_ENABLED. Bu duruma sahip olmayan bir düğme Kullanıcı girişini kabul etmez ve gri renkte olur.

- TBSTATE_HIDDEN düğme görünür değil ve Kullanıcı girişi alamıyor.

- Düğme gri TBSTATE_INDETERMINATE.

- Düğme basıldığında TBSTATE_PRESSED.

- Bir satır sonu TBSTATE_WRAP düğmeyi izler. Düğme de TBSTATE_ENABLED sahip olmalıdır.

*fsType*<br/>
'ndaki Düğmenin durum bayrakları. Aşağıdakilerden biri veya daha fazlası olabilir:

- TBSTYLE_BUTTON standart bir Gönder düğmesi oluşturur.

- TBSTYLE_CHECK, Kullanıcı tarafından her tıkladıktan sonra basılan ve basılmamış durumlar arasında geçiş yapan bir düğme oluşturur. Düğme, basılan durumda olduğunda farklı bir arka plan rengine sahiptir.

- TBSTYLE_CHECKGROUP, gruptaki başka bir düğmeye basılana kadar basılı kalan bir onay düğmesi oluşturur.

- TBSTYLE_GROUP, gruptaki başka bir düğmeye basılana kadar basılı kalan bir düğme oluşturur.

- TBSTYLE_SEP, düğme grupları arasında küçük bir boşluk sağlayan bir ayırıcı oluşturur. Bu stile sahip bir düğme Kullanıcı girişi almaz.

## <a name="csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a> Csnapınitemımpl:: UpdateMenuState

Bir menü öğesini, ek bileşen nesnesinin bağlam menüsüne eklenmeden önce değiştirmek için bu işlevi çağırın.

```cpp
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Ayarlanacak menü öğesinin KIMLIĞI.

*Parabelleğe*<br/>
'ndaki Güncelleştirileceği menü öğesi için dizeye yönelik bir işaretçi.

*bayraklar*<br/>
'ndaki Yeni durum bayraklarını belirtir. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- MF_POPUP, bunun bağlam menüsü içinde bir alt menü olduğunu belirtir. Menü öğeleri, ekleme noktaları ve diğer alt menüler bu alt menüye, olarak kullanılarak eklenebilir `lCommandID` `IInsertionPointID` .

- MF_BITMAP ve MF_OWNERDRAW bu bayraklara izin verilmez ve E_INVALIDARG dönüş değerine neden olur.

- MF_SEPARATOR yatay bölme çizgisi çizer. Yalnızca `IContextMenuProvider` MF_SEPARATOR kümesine sahip menü öğeleri eklemesine izin verilir.

- MF_CHECKED menü öğesinin yanına bir onay işareti koyar.

- MF_DISABLED menü öğesini devre dışı bırakır, bu nedenle seçilemez, ancak bayrak ona gri olmaz.

- MF_ENABLED, menü öğesinin seçilebilmesi için bu öğenin gri olan durumuna geri yükleyerek etkinleştirilir.

- MF_GRAYED menü öğesini devre dışı bırakır, böylece seçilemez.

- MF_MENUBARBREAK, bir menü çubuğu için MF_MENUBREAK bayrağıyla aynı şekilde çalışır. Açılan menü, alt menü veya kısayol menüsü için yeni sütun, eski sütundan dikey bir çizgi ile ayrılır.

- MF_MENUBREAK, sütunları ayırmak zorunda kalmadan öğeyi yeni bir satıra (bir menü çubuğu için) veya yeni bir sütuna (açılan menü, alt menü veya kısayol menüsü için) koyar.

- MF_UNCHECKED öğenin yanına bir onay işareti yerleştirmez (varsayılan).

Aşağıdaki bayrak grupları birlikte kullanılamaz:

- MF_DISABLED, MF_ENABLED ve MF_GRAYED.

- MF_MENUBARBREAK ve MF_MENUBREAK.

- MF_CHECKED ve MF_UNCHECKED.

## <a name="csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a> Csnapınitemımpl:: UpdateToolbarButton

Bu işlevi, ek bileşen nesnesinin görüntülenmeden önce bir araç çubuğu düğmesini değiştirmek için çağırın.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Güncelleştirileceği araç çubuğu düğmesinin düğme KIMLIĞINI belirtir.

*fsState*<br/>
Bir araç çubuğu düğme durumunu belirtir. Bu durum ayarlandıysanız, doğru döndürün. Bu, aşağıdaki bayrakların bir birleşimi olabilir:

- ETKIN düğme Kullanıcı girişini kabul eder. Bu duruma sahip olmayan bir düğme Kullanıcı girişini kabul etmez ve gri renkte olur.

- IŞARETLENMIŞ düğme IŞARETLI stile sahip ve basılmakta.

- GIZLI düğme görünür değildir ve Kullanıcı girişi alamaz.

- BELIRSIZ düğme gri.

- Düğmeye BASıLDıĞıNDA düğmeye basıldı.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
