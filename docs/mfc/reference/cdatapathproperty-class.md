---
description: 'Daha fazla bilgi edinin: CDataPathProperty sınıfı'
title: CDataPathProperty sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 7d9ff9f380fd44d5261374879bab63c9925c4442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247962"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty sınıfı

Zaman uyumsuz olarak yüklenebilen bir OLE denetim özelliği uygular.

## <a name="syntax"></a>Syntax

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDataPathProperty:: CDataPathProperty](#cdatapathproperty)|Bir `CDataPathProperty` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDataPathProperty:: GetControl](#getcontrol)|Nesneyle ilişkili zaman uyumsuz OLE denetimini alır `CDataPathProperty` .|
|[CDataPathProperty:: GetPath](#getpath)|Özelliğin yol adını alır.|
|[CDataPathProperty:: Open](#open)|İlişkili ActiveX (OLE) denetimi için zaman uyumsuz özelliği yüklemeyi başlatır.|
|[CDataPathProperty:: ResetData](#resetdata)|`CAsyncMonikerFile::OnDataAvailable`Kapsayıcıyı denetim özelliklerinin değiştiğini bildirmek için çağırır.|
|[CDataPathProperty:: SetControl](#setcontrol)|Özelliği ile ilişkili, zaman uyumsuz ActiveX (OLE) denetimini ayarlar.|
|[CDataPathProperty:: SetPath](#setpath)|Özelliğin yol adını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Zaman uyumsuz özellikler, zaman uyumlu başlatma işleminden sonra yüklenir.

Sınıfı `CDataPathProperty` öğesinden türetilir `CAysncMonikerFile` . OLE denetimleriniz içinde zaman uyumsuz özellikler uygulamak için, öğesinden bir sınıf türetirsiniz `CDataPathProperty` ve [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)öğesini geçersiz kılın.

Internet uygulamalarında zaman uyumsuz bilinen adlar ve ActiveX denetimleri kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Internet Ilk adımları: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)

- [Internet Ilk adımları: zaman uyumsuz bilinen adlar](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[Cotastreamfile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a> CDataPathProperty:: CDataPathProperty

Bir `CDataPathProperty` nesnesi oluşturur.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Bu nesneyle ilişkilendirilecek OLE denetim nesnesine yönelik bir işaretçi `CDataPathProperty` .

*lpszPath*<br/>
Mutlak veya göreli olabilen yol, özelliğin gerçek mutlak konumuna başvuran bir zaman uyumsuz bilinen ad oluşturmak için kullanılır. `CDataPathProperty` dosya adlarını değil, URL 'Leri kullanır. `CDataPathProperty`Bir dosya için bir nesne istiyorsanız yolu sonuna ekleyin `file://` .

### <a name="remarks"></a>Açıklamalar

`COleControl` *PControl* tarafından işaret edilen nesne tarafından kullanılır `Open` ve türetilmiş sınıflar tarafından alınır. *PControl* null ise, ile birlikte kullanılan denetim `Open` ile ayarlanmalıdır `SetControl` . *LPSZPATH* null ise, yolu aracılığıyla geçirebilir `Open` veya olarak ayarlayabilirsiniz `SetPath` .

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a> CDataPathProperty:: GetControl

Nesneyle ilişkili nesneyi almak için bu üye işlevini çağırın `COleControl` `CDataPathProperty` .

```
COleControl* GetControl();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili OLE denetimine yönelik bir işaretçi döndürür `CDataPathProperty` . Denetim ilişkilendirilmediği takdirde NULL.

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a> CDataPathProperty:: GetPath

Yolu almak için bu üye işlevi çağırın, `CDataPathProperty` nesne oluşturulduğunda veya içinde belirtildiğinde `Open` ya da member işlevine yapılan önceki çağrıda belirtilen şekilde ayarlanır `SetPath` .

```
CString GetPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelliğin kendi yol adını döndürür. Hiçbir yol belirtilmemişse boş olabilir.

## <a name="cdatapathpropertyopen"></a><a name="open"></a> CDataPathProperty:: Open

İlişkili denetimin zaman uyumsuz özelliğini yüklemeyi başlatmak için bu üye işlevi çağırın.

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Bu nesneyle ilişkilendirilecek OLE denetim nesnesine yönelik bir işaretçi `CDataPathProperty` .

*pError*<br/>
Bir dosya özel durumunun işaretçisi. Bir hata durumunda nedenine ayarlanır.

*lpszPath*<br/>
Mutlak veya göreli olabilen yol, özelliğin gerçek mutlak konumuna başvuran bir zaman uyumsuz bilinen ad oluşturmak için kullanılır. `CDataPathProperty` dosya adlarını değil, URL 'Leri kullanır. `CDataPathProperty`Bir dosya için bir nesne istiyorsanız yolu sonuna ekleyin `file://` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev, denetimden arabirimi edinmeye çalışır `IBindHost` .

`Open`Yol olmadan çağrılmadan önce, özelliğin yolunun değeri ayarlanmalıdır. Bu, nesne oluşturulduğunda veya `SetPath` üye işlevi çağırarak yapılabilir.

`Open`Bir denetim olmadan çağrılmadan önce, bir ActiveX denetimi (daha önce OLE denetimi olarak bilinir) nesneyle ilişkili olabilir. Bu, nesne oluşturulduğunda ya da çağırarak yapılabilir `SetControl` .

[CAsyncMonikerFile:: Open](../../mfc/reference/casyncmonikerfile-class.md#open) 'ın tüm aşırı yüklemeleri ' de kullanılabilir `CDataPathProperty` .

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a> CDataPathProperty:: ResetData

`CAsyncMonikerFile::OnDataAvailable`Kapsayıcıya denetim özelliklerinin değiştiğini bildirmek için bu işlevi çağırın ve zaman uyumsuz olarak yüklenen tüm bilgiler artık yararlı değildir.

```
virtual void ResetData();
```

### <a name="remarks"></a>Açıklamalar

Açma yeniden başlatılmalıdır. Türetilmiş sınıflar, farklı varsayılanlar için bu işlevi geçersiz kılabilir.

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a> CDataPathProperty:: SetControl

Zaman uyumsuz bir OLE denetimini nesnesiyle ilişkilendirmek için bu üye işlevini çağırın `CDataPathProperty` .

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Özelliği ile ilişkilendirilecek zaman uyumsuz OLE denetimine yönelik bir işaretçi.

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a> CDataPathProperty:: SetPath

Özelliğin yol adını ayarlamak için bu üye işlevini çağırın.

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
Zaman uyumsuz olarak yüklenen özelliğe mutlak veya göreli olabilen bir yol. `CDataPathProperty` dosya adlarını değil, URL 'Leri kullanır. `CDataPathProperty`Bir dosya için bir nesne istiyorsanız yolu sonuna ekleyin `file://` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek resmi](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile sınıfı](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
