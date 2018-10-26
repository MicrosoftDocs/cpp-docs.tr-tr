---
title: CCachedDataPathProperty sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06a35f51b821d7c8e5b31806a96ac2bde0d0474a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054338"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty sınıfı

Uygulayan bir OLE denetim, zaman uyumsuz olarak aktarılabilen ve bir bellek dosyasında önbelleğe özelliği.

## <a name="syntax"></a>Sözdizimi

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Oluşturur bir `CCachedDataPathProperty` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile` verileri önbelleğe nesne içine.|

## <a name="remarks"></a>Açıklamalar

Bellek dosya RAM yerine diskte depolanır ve hızlı bir geçici aktarımları için kullanışlıdır.

İle birlikte `CAysncMonikerFile` ve `CDataPathProperty`, `CCachedDataPathProperty` OLE denetimleri içinde zaman uyumsuz adların kullanılması için işlevsellik sağlar. İle `CCachedDataPathProperty` nesneler, verileri zaman uyumsuz olarak bir URL veya dosya kaynaktan aktarmak ve bir bellek dosyasında depolamak için `m_Cache` genel değişkeni. Tüm verileri, bellek dosyasında depolanır ve geçersiz kılmak için gerek yoktur [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) bildirimleri için izlemek ve yanıtlamak istemediğiniz sürece. Örneğin, bir büyük aktarıyorsanız. GIF dosyası ve daha fazla veri geldi ve bu kendisi yeniden çizmeniz gerekir denetiminiz bildirmek istiyorsanız geçersiz kılma `OnDataAvailable` bildirim yapmak.

Sınıf `CCachedDataPathProperty` türetilir `CDataPathProperty`.

Zaman uyumsuz adlar ve ActiveX denetimleri, Internet uygulamalarında kullanma hakkında daha fazla bilgi için aşağıdaki konulara bakın:

- [Internet ilk adımlar: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)

- [Internet ilk adımlar: Zaman uyumsuz adlar](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="ccacheddatapathproperty"></a>  CCachedDataPathProperty::CCachedDataPathProperty

Oluşturur bir `CCachedDataPathProperty` nesne.

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Şununla ilişkili olmasını ActiveX denetimi nesneye bir işaretçi `CCachedDataPathProperty` nesne.

*lpszPath*<br/>
Mutlak veya göreli olabilir, yolun özelliği gerçek mutlak konumunu başvuran bir zaman uyumsuz bir bilinen ad oluşturmak için kullanılır. `CCachedDataPathProperty` URL değil dosya adlarını kullanır. İsterseniz bir `CCachedDataPathProperty` nesne için bir dosya, file:// yolunun önüne ekleyin.

### <a name="remarks"></a>Açıklamalar

`COleControl` Nesne tarafından işaret edilen *pControl* tarafından kullanılan [açık](../../mfc/reference/cdatapathproperty-class.md#open) ve türetilmiş sınıflar tarafından alınır. Varsa *pControl* null ile kullanılan denetimi `Open` ile ayarlanmalıdır [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Varsa *lpszPath* NULL ise yolunda geçirebilirsiniz `Open` veya ile ayarlayın [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).

##  <a name="m_cache"></a>  CCachedDataPathProperty::m_Cache

Hangi veriler önbelleğe bellek dosyasının sınıf adını içerir.

```
CMemFile m_Cache;
```

### <a name="remarks"></a>Açıklamalar

Bellek dosya RAM yerine diskte depolanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDataPathProperty Sınıfı](../../mfc/reference/cdatapathproperty-class.md)
