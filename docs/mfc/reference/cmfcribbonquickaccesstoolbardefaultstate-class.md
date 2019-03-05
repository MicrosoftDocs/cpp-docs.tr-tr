---
title: CMFCRibbonQuickAccessToolBarDefaultState sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: 0ea9ec8de0b657fa4e7c601f9c3e676f550defa9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302487"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState sınıfı

Şerit çubuğundaki konumlandırılmış hızlı erişim araç için varsayılan duruma yöneten bir yardımcı sınıfı ( [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)).

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Oluşturur bir `CMFCRibbonQuickAccessToolbarDefaultState` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|Bir komut için hızlı erişim araç çubuğu varsayılan durumuna ekler. Bu araç değiştirmez.|
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Bir hızlı erişim araç çubuğu özelliklerini diğerine kopyalar.|
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Tüm komutlar, Hızlı Erişim Araç Çubuğu ' kaldırır. Bu araç değiştirmez.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda hızlı erişim araç çubuğu oluşturduktan sonra varsayılan durumuna çağırarak ayarlamanızı öneririz [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate). Kullanıcı tıkladığında bu varsayılan durumunun geri yüklendiği **sıfırlama** düğmesini **Özelleştir** uygulamanızın sayfasında **seçenekleri** iletişim kutusu.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonQuickAccessToolbarDefaultState` sınıfı ve nasıl hızlı erişim araç çubuğu için varsayılan duruma komut ekleme.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribbonquickaccesstoolbar.h

##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand

Bir komut için hızlı erişim araç çubuğu varsayılan durumuna ekler.

```
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*[in] uiCmd*<br/>
Komut kimliğini belirtir.

*[in] bIsVisible*<br/>
Hızlı Erişim Araç çubuğu varsayılan durumda olduğunda komut görünürlüğünü belirler.

### <a name="remarks"></a>Açıklamalar

Komut için CMFCRibbonQuickAccessToolBarDefaultState ekleme olarak üç sonuçtan gerçekleştirir. İlk olarak, eklenen her komut hızlı erişim araç çubuğunun sağ tarafında açılan listelenir. Bu şekilde, kullanıcı bir kolayca ekleyebilir veya hızlı erişim araç çubuğundan bu komutu kaldırın. İkinci olarak, hızlı erişim araç çubuğu kullanıcı tıkladığında listelenen komutlar varsayılan durumunda görünür olarak göstermek için sıfırlama **sıfırlama** düğmesine **Özelleştir** iletişim kutusu. Değil çağrılırsa üçüncü [CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands), hızlı erişim araç çubuğu görünür komutlar bu listeden varsayılan görünür komutları bir kullanıcı uygulamanızı ilk kez çalıştırdığında kullanır. İstediğiniz tüm komutları ekledikten sonra çağrı [CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) Bu örnek, Şerit çubuğunun hızlı erişim araç için varsayılan duruma ayarlamak için.

##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom

Bir hızlı erişim araç çubuğu özelliklerini diğerine kopyalar.

```
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kaynak başvuru `CMFCRibbonQuickAccessToolBarDefaultState` kopyalanacak nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, her komutun kaynaktan kopyalar `CMFCRibbonQuickAccessToolBarDefaultState` kullanarak bu nesne için nesne [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) yöntemi.

##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

Hızlı Erişim Araç çubuğu varsayılan durum nesnesi oluşturur.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, listesini komutları, yeni bir örneğini [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) içeren boş.

##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll

Hızlı Erişim Araç çubuğu varsayılan komutların listesini temizler.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, tüm komutlar bu örneğinden kaldırır, önceki çağrıları [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand) eklendi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
