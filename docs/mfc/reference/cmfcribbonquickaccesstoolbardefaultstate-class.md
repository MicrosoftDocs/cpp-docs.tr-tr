---
description: 'Daha fazla bilgi edinin: CMFCRibbonQuickAccessToolBarDefaultState sınıfı'
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
ms.openlocfilehash: d6cd0c32cd8698259de0a78a6a6a7dc42012e92f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321819"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState sınıfı

Şerit çubuğunda ( [CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)) konumlandırılmış olan hızlı erişim araç çubuğunun varsayılan durumunu yöneten bir yardımcı sınıf.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState:: CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Bir `CMFCRibbonQuickAccessToolbarDefaultState` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand)|Hızlı erişim araç çubuğu için varsayılan duruma bir komut ekler. Bu, araç çubuğunun kendisini değiştirmez.|
|[CMFCRibbonQuickAccessToolBarDefaultState:: CopyFrom](#copyfrom)|Bir hızlı erişim araç çubuğunun özelliklerini diğerine kopyalar.|
|[CMFCRibbonQuickAccessToolBarDefaultState:: RemoveAll](#removeall)|Hızlı erişim araç çubuğundan tüm komutları kaldırır. Bu, araç çubuğunun kendisini değiştirmez.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda hızlı erişim araç çubuğunu oluşturduktan sonra, [CMFCRibbonBar:: SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)komutunu çağırarak varsayılan durumunu ayarlamanızı öneririz. Bu varsayılan durum, bir kullanıcı uygulamanızın **Seçenekler** Iletişim kutusunun **Özelleştir** sayfasında **Sıfırla** düğmesine tıkladığında geri yüklenir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu `CMFCRibbonQuickAccessToolbarDefaultState` ve hızlı erişim araç çubuğu için varsayılan duruma bir komut nasıl ekleneceğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonquickaccesstoolbar. h

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a> CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand

Hızlı erişim araç çubuğu için varsayılan duruma bir komut ekler.

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Parametreler

*[in] Uııcmd*<br/>
Komut KIMLIĞINI belirtir.

*[in] bIsVisible*<br/>
Hızlı erişim araç çubuğu varsayılan durumundaysa, komutun görünürlüğünü ayarlar.

### <a name="remarks"></a>Açıklamalar

CMFCRibbonQuickAccessToolBarDefaultState komutuna bir komut eklemek üç sonuç gerçekleştirir. İlk olarak, eklenen her komut hızlı erişim araç çubuğunun sağ tarafındaki açılır menüde listelenir. Bu şekilde, bir kullanıcı hızlı erişim araç çubuğundan bu komutu kolayca ekleyebilir veya kaldırabilir. İkinci olarak, hızlı erişim araç çubuğu, Kullanıcı **Özelleştir** Iletişim kutusunda **Sıfırla** düğmesine tıkladığında varsayılan durumda görünür olarak listelenen komutları gösterecek şekilde sıfırlanır. Üçüncü olarak, [CMFCRibbonBar:: SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)' i çağırdıysanız, hızlı erişim araç çubuğu, Kullanıcı uygulamanızı ilk kez çalıştırdığında varsayılan görünür komutlar olarak bu listedeki görünür komutları kullanır. İstediğiniz tüm komutları ekledikten sonra bu örneği, bu şerit çubuğunun hızlı erişim araç çubuğunun varsayılan durumu olarak ayarlamak için [CMFCRibbonBar:: SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) komutunu çağırın.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a> CMFCRibbonQuickAccessToolBarDefaultState:: CopyFrom

Bir hızlı erişim araç çubuğunun özelliklerini diğerine kopyalar.

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
'ndaki Kopyalanacak kaynak nesnesine bir başvuru `CMFCRibbonQuickAccessToolBarDefaultState` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCRibbonQuickAccessToolBarDefaultState` [CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand) metodunu kullanarak her komutu kaynak nesnesinden bu nesneye kopyalar.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a> CMFCRibbonQuickAccessToolBarDefaultState:: CMFCRibbonQuickAccessToolBarDefaultState

Hızlı erişim araç çubuğu varsayılan durum nesnesini oluşturur.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [Cmfribbonquickaccesstoolbardefaultstate](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) öğesinin yeni örneğinin içerdiği komutların listesi boştur.

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a> CMFCRibbonQuickAccessToolBarDefaultState:: RemoveAll

Hızlı erişim araç çubuğundaki varsayılan komutların listesini temizler.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, önceki [CMFCRibbonQuickAccessToolBarDefaultState:: AddCommand](#addcommand) öğesine yapılan önceki çağrıların eklendiği tüm komutları bu örnekten kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
