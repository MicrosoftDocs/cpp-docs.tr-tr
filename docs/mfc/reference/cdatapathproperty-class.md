---
title: CDataPathProperty Sınıfı
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
ms.openlocfilehash: e96106dcd6f496c6cc99c9d72d86052547b6d06b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376464"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty Sınıfı

Eş senkronize olarak yüklenebilen bir OLE denetim özelliği uygular.

## <a name="syntax"></a>Sözdizimi

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CdataPathÖzelliği::CdataPathÖzelliği](#cdatapathproperty)|Bir `CDataPathProperty` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDataPathÖzelliği::GetControl](#getcontrol)|Nesneyle ilişkili eşzamanlı OLE denetimini `CDataPathProperty` alır.|
|[CDataPathÖzelliği::GetPath](#getpath)|Özelliğin yol adını alır.|
|[CDataPathÖzelliği::Aç](#open)|İlişkili ActiveX (OLE) denetimi için eşzamanlı özelliğin yüklenmesi nin başlatılmasını sağlar.|
|[CDataPathProperty::ResetData](#resetdata)|Denetim `CAsyncMonikerFile::OnDataAvailable` özelliklerinin değiştiğini kapsayıcıya bildirmek için çağrılar.|
|[CDataPathÖzelliği::SetControl](#setcontrol)|Özellik ile ilişkili eşzamanlı ActiveX (OLE) denetimini ayarlar.|
|[CDataPathÖzelliği::SetPath](#setpath)|Özelliğin yol adını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Senkron inisiyasyondan sonra asynchronous özellikleri yüklenir.

Sınıf `CDataPathProperty` `CAysncMonikerFile`türetilmiştir. OLE denetimlerinizde eşzamanlı özellikler uygulamak için, bir `CDataPathProperty`sınıf türetin ve [OnDataAvailable'ı](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)geçersiz kılın.

Internet uygulamalarında eşzamanlı monikers ve ActiveX denetimlerinin nasıl kullanılacağı hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [İnternet İlk Adımlar: ActiveX Denetimleri](../../mfc/activex-controls-on-the-internet.md)

- [İnternet İlk Adımlar: Asynchronous Monikers](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerDosya](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerDosya](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a>CdataPathÖzelliği::CdataPathÖzelliği

Bir `CDataPathProperty` nesne inşa eder.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pKontrol*<br/>
Bu `CDataPathProperty` nesneyle ilişkilendirilecek OLE denetim nesnesine işaretçi.

*lpszPath*<br/>
Mutlak veya göreceli olabilecek yol, özelliğin gerçek mutlak konumuna başvuran eşzamanlı bir takma sözcük oluşturmak için kullanılır. `CDataPathProperty`URL'leri kullanır, dosya adlarını değil. Dosya için `CDataPathProperty` bir nesne istiyorsanız, `file://` yola hazırlayın.

### <a name="remarks"></a>Açıklamalar

*pControl* tarafından işaret edilen `Open` `COleControl` nesne türemiş sınıflar tarafından kullanılır ve alınır. *pControl* NULL ise, kullanılan `Open` denetim . `SetControl` *lpszPath* NULL ise, yoldan geçebilir `Open` veya ' ile `SetPath`ayarlayabilirsiniz.

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a>CDataPathÖzelliği::GetControl

Nesneyle ilişkili `COleControl` nesneyi almak için `CDataPathProperty` bu üye işlevi çağırın.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili OLE denetimine `CDataPathProperty` bir işaretçi döndürür. NULL değilse denetim ilişkilidir.

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a>CDataPathÖzelliği::GetPath

Nesney oluşturulduğunda veya `CDataPathProperty` `Open` `SetPath` üye işleve önceki bir çağrıda belirtildiğinde ayarlanan yolu almak için bu üye işlevi çağırın.

```
CString GetPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yol adını özelliğin kendisine verir. Yol belirtilmemişse boş olabilir.

## <a name="cdatapathpropertyopen"></a><a name="open"></a>CDataPathÖzelliği::Aç

İlişkili denetim için eşzamanlı özelliğin yüklenmesi için bu üye işlevi arayın.

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

*pKontrol*<br/>
Bu `CDataPathProperty` nesneyle ilişkilendirilecek OLE denetim nesnesine işaretçi.

*pHata*<br/>
Dosya özel durum için bir işaretçi. Bir hata durumunda, neden ayarlanır.

*lpszPath*<br/>
Mutlak veya göreceli olabilecek yol, özelliğin gerçek mutlak konumuna başvuran eşzamanlı bir takma sözcük oluşturmak için kullanılır. `CDataPathProperty`URL'leri kullanır, dosya adlarını değil. Dosya için `CDataPathProperty` bir nesne istiyorsanız, `file://` yola hazırlayın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlev, `IBindHost` denetimden arabirimi elde etmeye çalışır.

Yol `Open` olmadan aramadan önce, özelliğin yolunun değeri ayarlanmalıdır. Bu, nesne oluşturulduğunda veya `SetPath` üye işlevi çağırarak yapılabilir.

Denetim `Open` olmadan aramadan önce, activex denetimi (eski adıyla OLE denetimi olarak bilinir) nesneyle ilişkilendirilebilir. Bu, nesne oluşturulduğunda veya . `SetControl`

[CAsyncMonikerFile tüm aşırı yükleri::Açık](../../mfc/reference/casyncmonikerfile-class.md#open) `CDataPathProperty`da mevcuttur .

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a>CDataPathProperty::ResetData

Denetim özelliklerinin `CAsyncMonikerFile::OnDataAvailable` değiştiğini ve eşzamanlı olarak yüklenen tüm bilgilerin artık kullanışlı olmadığını kapsayıcıya bildirmek için bu işlevi arayın.

```
virtual void ResetData();
```

### <a name="remarks"></a>Açıklamalar

Açılış yeniden başlatılmalıdır. Türetilen sınıflar farklı varsayılanlar için bu işlevi geçersiz kılabilir.

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a>CDataPathÖzelliği::SetControl

`CDataPathProperty` Nesne ile bir eşzamanlı OLE denetimi ilişkilendirmek için bu üye işlevi arayın.

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Parametreler

*pKontrol*<br/>
Özellik ile ilişkili olmak için eşzamanlı OLE denetimi için bir işaretçi.

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a>CDataPathÖzelliği::SetPath

Özelliğin yol adını ayarlamak için bu üye işlevi arayın.

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
Mutlak veya göreceli olabilecek bir yol, eşit olarak yüklenen özellik için. `CDataPathProperty`URL'leri kullanır, dosya adlarını değil. Dosya için `CDataPathProperty` bir nesne istiyorsanız, `file://` yola hazırlayın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek Görüntü](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
