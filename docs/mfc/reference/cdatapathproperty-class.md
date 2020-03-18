---
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
ms.openlocfilehash: 89cb8ddcdd42643f52f755516e8845109163c57a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418694"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty sınıfı

Zaman uyumsuz olarak yüklenebilen bir OLE denetim özelliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDataPathProperty:: CDataPathProperty](#cdatapathproperty)|`CDataPathProperty` nesnesi oluşturur.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDataPathProperty:: GetControl](#getcontrol)|`CDataPathProperty` nesnesiyle ilişkili zaman uyumsuz OLE denetimini alır.|
|[CDataPathProperty:: GetPath](#getpath)|Özelliğin yol adını alır.|
|[CDataPathProperty:: Open](#open)|İlişkili ActiveX (OLE) denetimi için zaman uyumsuz özelliği yüklemeyi başlatır.|
|[CDataPathProperty:: ResetData](#resetdata)|Kapsayıcıyı denetim özelliklerinin değiştiğini bildirmek için `CAsyncMonikerFile::OnDataAvailable` çağırır.|
|[CDataPathProperty:: SetControl](#setcontrol)|Özelliği ile ilişkili, zaman uyumsuz ActiveX (OLE) denetimini ayarlar.|
|[CDataPathProperty:: SetPath](#setpath)|Özelliğin yol adını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Zaman uyumsuz özellikler, zaman uyumlu başlatma işleminden sonra yüklenir.

`CDataPathProperty` sınıfı `CAysncMonikerFile`türetilir. OLE denetimleriniz içinde zaman uyumsuz özellikler uygulamak için, `CDataPathProperty`bir sınıf türetirsiniz ve [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)öğesini geçersiz kılın.

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

##  <a name="cdatapathproperty"></a>CDataPathProperty:: CDataPathProperty

`CDataPathProperty` nesnesi oluşturur.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Bu `CDataPathProperty` nesnesiyle ilişkilendirilecek OLE denetim nesnesine yönelik bir işaretçi.

*lpszPath*<br/>
Mutlak veya göreli olabilen yol, özelliğin gerçek mutlak konumuna başvuran bir zaman uyumsuz bilinen ad oluşturmak için kullanılır. `CDataPathProperty`, dosya adlarını değil, URL 'Leri kullanır. Bir dosya için `CDataPathProperty` nesnesi istiyorsanız yola `file://` ekleyin.

### <a name="remarks"></a>Açıklamalar

*PControl* tarafından işaret edilen `COleControl` nesnesi `Open` tarafından kullanılır ve türetilmiş sınıflar tarafından alınır. *PControl* null ise, `Open` ile kullanılan denetim `SetControl`olarak ayarlanmalıdır. *LPSZPATH* null ise, yolu `Open` aracılığıyla geçirebilir veya `SetPath`olarak ayarlayabilirsiniz.

##  <a name="getcontrol"></a>CDataPathProperty:: GetControl

`CDataPathProperty` nesnesiyle ilişkili `COleControl` nesnesini almak için bu üye işlevi çağırın.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Dönüş Değeri

`CDataPathProperty` nesnesiyle ilişkili OLE denetimine yönelik bir işaretçi döndürür. Denetim ilişkilendirilmediği takdirde NULL.

##  <a name="getpath"></a>CDataPathProperty:: GetPath

Yolu almak için bu üye işlevi çağırın, `CDataPathProperty` nesne oluşturulduğunda ayarlayın veya `Open`veya `SetPath` üye işlevine yapılan bir önceki çağrıda belirtilir.

```
CString GetPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özelliğin kendi yol adını döndürür. Hiçbir yol belirtilmemişse boş olabilir.

##  <a name="open"></a>CDataPathProperty:: Open

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
Bu `CDataPathProperty` nesnesiyle ilişkilendirilecek OLE denetim nesnesine yönelik bir işaretçi.

*pError*<br/>
Bir dosya özel durumunun işaretçisi. Bir hata durumunda nedenine ayarlanır.

*lpszPath*<br/>
Mutlak veya göreli olabilen yol, özelliğin gerçek mutlak konumuna başvuran bir zaman uyumsuz bilinen ad oluşturmak için kullanılır. `CDataPathProperty`, dosya adlarını değil, URL 'Leri kullanır. Bir dosya için `CDataPathProperty` nesnesi istiyorsanız yola `file://` ekleyin.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev, denetimden `IBindHost` arabirimini almaya çalışır.

Yol olmadan `Open` çağrılmadan önce, özelliğin yolunun değeri ayarlanmalıdır. Bu, nesne oluşturulduğunda veya `SetPath` üye işlevi çağırarak yapılabilir.

Bir denetim olmadan `Open` çağrılmadan önce, bir ActiveX denetimi (daha önce OLE denetimi olarak bilinir) nesneyle ilişkilendirilebilir. Bu, nesne oluşturulduğunda veya `SetControl`çağırarak yapılabilir.

[CAsyncMonikerFile:: Open](../../mfc/reference/casyncmonikerfile-class.md#open) ' ın tüm aşırı yüklemeleri de `CDataPathProperty`de mevcuttur.

##  <a name="resetdata"></a>CDataPathProperty:: ResetData

Kapsayıcıya denetim özellikleri değiştiği ve zaman uyumsuz olarak yüklenen tüm bilgiler artık yararlı olmadığı için `CAsyncMonikerFile::OnDataAvailable` almak için bu işlevi çağırın.

```
virtual void ResetData();
```

### <a name="remarks"></a>Açıklamalar

Açma yeniden başlatılmalıdır. Türetilmiş sınıflar, farklı varsayılanlar için bu işlevi geçersiz kılabilir.

##  <a name="setcontrol"></a>CDataPathProperty:: SetControl

Zaman uyumsuz bir OLE denetimini `CDataPathProperty` nesnesiyle ilişkilendirmek için bu üye işlevini çağırın.

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Özelliği ile ilişkilendirilecek zaman uyumsuz OLE denetimine yönelik bir işaretçi.

##  <a name="setpath"></a>CDataPathProperty:: SetPath

Özelliğin yol adını ayarlamak için bu üye işlevini çağırın.

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
Zaman uyumsuz olarak yüklenen özelliğe mutlak veya göreli olabilen bir yol. `CDataPathProperty`, dosya adlarını değil, URL 'Leri kullanır. Bir dosya için `CDataPathProperty` nesnesi istiyorsanız yola `file://` ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek resmi](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
