---
description: 'Daha fazla bilgi edinin: CCachedDataPathProperty sınıfı'
title: CCachedDataPathProperty sınıfı
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
ms.openlocfilehash: a61d2553afc4415da29399293843deb1be5f113d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122505"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty sınıfı

Zaman uyumsuz olarak aktarılan ve bir bellek dosyasında önbelleğe alınmış bir OLE denetim özelliği uygular.

## <a name="syntax"></a>Syntax

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCachedDataPathProperty:: CCachedDataPathProperty](#ccacheddatapathproperty)|Bir `CCachedDataPathProperty` nesnesi oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCachedDataPathProperty:: m_Cache](#m_cache)|`CMemFile` verilerin önbelleğe alınacağı nesne.|

## <a name="remarks"></a>Açıklamalar

Bellek dosyası, disk yerine RAM 'de depolanır ve hızlı geçici aktarımlar için kullanışlıdır.

Ve ile `CAysncMonikerFile` birlikte `CDataPathProperty` , `CCachedDataPathProperty` OLE denetimlerinde zaman uyumsuz bilinen adların kullanılması için işlevsellik sağlar. `CCachedDataPathProperty`Nesneler ile, verileri BIR URL veya dosya kaynağından zaman uyumsuz olarak aktarabilir ve genel değişken aracılığıyla bir bellek dosyasında depolayabileceksiniz `m_Cache` . Tüm veriler bellek dosyasında depolanır ve bildirim ve yanıt vermeyi izlemek istemediğiniz müddetçe [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) öğesinin geçersiz kılınmasına gerek yoktur. Örneğin, büyük bir aktarıyorsanız. GIF dosyası ve denetime daha fazla veri geldiğini bildirmek ve bu bildirimin kendisini yeniden `OnDataAvailable` çizmesi gerekir, bildirimi yapmak için geçersiz kılın.

Sınıfı `CCachedDataPathProperty` öğesinden türetilir `CDataPathProperty` .

Internet uygulamalarında zaman uyumsuz bilinen adlar ve ActiveX denetimleri kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Internet Ilk adımları: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)

- [Internet Ilk adımları: zaman uyumsuz bilinen adlar](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[Cotastreamfile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a> CCachedDataPathProperty:: CCachedDataPathProperty

Bir `CCachedDataPathProperty` nesnesi oluşturur.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Bu nesneyle ilişkilendirilecek ActiveX denetim nesnesine yönelik bir işaretçi `CCachedDataPathProperty` .

*lpszPath*<br/>
Mutlak veya göreli olabilen yol, özelliğin gerçek mutlak konumuna başvuran bir zaman uyumsuz bilinen ad oluşturmak için kullanılır. `CCachedDataPathProperty` dosya adlarını değil, URL 'Leri kullanır. `CCachedDataPathProperty`Bir dosya için bir nesne istiyorsanız, yolu File://önüne ekleyin.

### <a name="remarks"></a>Açıklamalar

`COleControl` *PControl* tarafından işaret edilen nesne, türetilmiş sınıflar tarafından [Açık](../../mfc/reference/cdatapathproperty-class.md#open) ve alınan tarafından kullanılır. *PCONTROL* null ise, ile birlikte kullanılan denetim `Open` [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)ile ayarlanmalıdır. *LPSZPATH* null ise, yolu aracılığıyla geçiş yapabilir `Open` veya [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)ile ayarlayabilirsiniz.

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a> CCachedDataPathProperty:: m_Cache

Verilerin önbelleğe alındığı bellek dosyasının sınıf adını içerir.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>Açıklamalar

Bellek dosyası, disk yerine RAM olarak depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[CDataPathProperty sınıfı](../../mfc/reference/cdatapathproperty-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDataPathProperty sınıfı](../../mfc/reference/cdatapathproperty-class.md)
