---
title: CMFCRibbonQuickAccessToolBarDefaultState Sınıf
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
ms.openlocfilehash: eb6b36066f34036ae599a94f4d1c07b2c633e730
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753516"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState Sınıf

Şerit çubuğunda [(CMFCRibbonBar Sınıfı)](../../mfc/reference/cmfcribbonbar-class.md)konumlandırılmış Hızlı Erişim Araç Çubuğu için varsayılan durumu yöneten bir yardımcı sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Bir `CMFCRibbonQuickAccessToolbarDefaultState` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::Addkomut](#addcommand)|Hızlı Erişim Araç Çubuğu için varsayılan duruma bir komut ekler. Bu, araç çubuğunun kendisini değiştirmez.|
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|Bir Hızlı Erişim Araç Çubuğu'nun özelliklerini diğerine kopyalar.|
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|Hızlı Erişim Araç Çubuğu'ndaki tüm komutları kaldırır. Bu, araç çubuğunun kendisini değiştirmez.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda Hızlı Erişim Araç Çubuğu'nu oluşturduktan [sonra, CMFCRibbonBar::SetQuickAccessDefaultState'i](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)arayarak varsayılan durumunu ayarlamanızı öneririz. Bir kullanıcı uygulamanızın **Seçenekler** iletişim kutusunun **Özelleştir** sayfasındaki **Sıfırla** düğmesini tıklattığında bu varsayılan durum geri yüklenir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCRibbonQuickAccessToolbarDefaultState` nasıl oluşturulabildiğini ve Hızlı Erişim Araç Çubuğu için varsayılan duruma komutun nasıl ekleyeceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonquickaccesstoolbar.h

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a>CMFCRibbonQuickAccessToolBarDefaultState::Addkomut

Hızlı Erişim Araç Çubuğu için varsayılan duruma bir komut ekler.

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*[in] uiCmd*<br/>
Komut kimliğini belirtir.

*[in] bIsVisible*<br/>
Hızlı Erişim Araç Çubuğu varsayılan durumdayken komutun görünürlüğünü ayarlar.

### <a name="remarks"></a>Açıklamalar

CMFCRibbonQuickAccessToolBarDefaultState'e komut eklemek üç sonuç verir. İlk olarak, eklenen her komut, Hızlı Erişim Araç Çubuğu'nun sağ tarafındaki açılır listede listelenir. Bu şekilde, bir kullanıcı bu komutu Hızlı Erişim Araç Çubuğu'ndan kolayca ekleyebilir veya kaldırabilir. İkinci olarak, Hızlı Erişim Araç Çubuğu, kullanıcı **Özelleştir** iletişim kutusunda **sıfırla** düğmesini tıklattığında yalnızca varsayılan durumda görünür olarak listelenen komutları göstermek için sıfırlanır. Üçüncü olarak, [CMFCRibbonBar::SetQuickAccessKomutları'nı](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)aramadıysanız, Hızlı Erişim Araç Çubuğu, varsayılan görünür komutlar bir kullanıcının uygulamanızı ilk çalıştırdığı sırada bu listeden görünür komutları kullanır. İstediğiniz tüm komutları ekledikten sonra [CMFCRibbonBar::SetQuickAccessDefaultState'i](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) arayarak bu örneği Şerit Çubuğu'nun Hızlı Erişim Araç Çubuğu için varsayılan durum olarak ayarlayın.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a>CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom

Bir Hızlı Erişim Araç Çubuğu'nun özelliklerini diğerine kopyalar.

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kopyalanması gereken `CMFCRibbonQuickAccessToolBarDefaultState` kaynak nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu `CMFCRibbonQuickAccessToolBarDefaultState` [yöntem, cmfcribbonQuickAccessToolToolDefaultState](#addcommand) kullanarak kaynak nesneden bu nesneye her komut kopyalar:AddCommand yöntemi.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a>CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

Hızlı Erişim Araç Çubuğu varsayılan durum nesnesini oluşturuyor.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CMFRibbonQuickAccessToolToolDefaultState'in](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) yeni örneğinin içerdiği komutlar listesi boştur.

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a>CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll

Hızlı Erişim Araç Çubuğu'ndaki varsayılan komutların listesini temizler.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, [cmfcribbonQuickAccessToolBDefaultState](#addcommand) önceki çağrıları tüm komutları bu örnekten kaldırır::AddCommand ekledi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
