---
title: CCachedDataPathProperty Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: ebab34433f23b119e3444b3eaa8b0ad6313555af
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352362"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty Sınıfı

Bir bellek dosyasında eşsenkronize ve önbelleğe alınmış bir OLE denetim özelliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Bir `CCachedDataPathProperty` nesne inşa eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CCachedDataPathÖzellik::m_Cache](#m_cache)|`CMemFile`verileri önbelleğe almak için nesne.|

## <a name="remarks"></a>Açıklamalar

Bellek dosyası diskte değil RAM'de depolanır ve hızlı geçici aktarımlar için yararlıdır.

OLE `CAysncMonikerFile` `CDataPathProperty`kontrollerinde eşzamanlı monikers kullanımı için işlevsellik `CCachedDataPathProperty` sağlar. Nesnelerle, `CCachedDataPathProperty` verileri bir URL veya dosya kaynağından eşit bir şekilde aktarabilir ve ortak `m_Cache` değişken üzerinden bir bellek dosyasında depolayabilirsiniz. Tüm veriler bellek dosyasında depolanır ve bildirimleri izlemek ve yanıt vermek istemediğiniz sürece [OnDataAvailable'ı](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) geçersiz kılmaya gerek yoktur. Örneğin, büyük bir . GIF dosyası ve daha fazla veri geldi ve bildirim yapmak için `OnDataAvailable` geçersiz kılmak, kendini yeniden çizmek gerektiğini kontrol bildirmek istiyorum.

Sınıf `CCachedDataPathProperty` `CDataPathProperty`türetilmiştir.

Internet uygulamalarında eşzamanlı monikers ve ActiveX denetimlerinin nasıl kullanılacağı hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [İnternet İlk Adımlar: ActiveX Denetimleri](../../mfc/activex-controls-on-the-internet.md)

- [İnternet İlk Adımlar: Asynchronous Monikers](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerDosya](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerDosya](../../mfc/reference/casyncmonikerfile-class.md)

[Cdatapathproperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty

Bir `CCachedDataPathProperty` nesne inşa eder.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pKontrol*<br/>
ActiveX denetim nesnesine işaretçibu `CCachedDataPathProperty` nesneyle ilişkilendirilecek.

*lpszPath*<br/>
Mutlak veya göreceli olabilecek yol, özelliğin gerçek mutlak konumuna başvuran eşzamanlı bir takma sözcük oluşturmak için kullanılır. `CCachedDataPathProperty`URL'leri kullanır, dosya adlarını değil. Bir dosya `CCachedDataPathProperty` için bir nesne istiyorsanız, yola hazırlık file://.

### <a name="remarks"></a>Açıklamalar

`COleControl` *pControl* tarafından işaret edilen nesne [Açık](../../mfc/reference/cdatapathproperty-class.md#open) tarafından kullanılır ve türemiş sınıflar tarafından alınır. *pControl* NULL ise, kullanılan `Open` denetim [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)ile ayarlanmalıdır. *lpszPath* NULL ise, yoldan geçebilir `Open` veya [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)ile ayarlayabilirsiniz.

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a>CCachedDataPathÖzellik::m_Cache

Verilerin önbelleğe aldığı bellek dosyasının sınıf adını içerir.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>Açıklamalar

Bellek dosyası diskte değil, RAM'de depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)
