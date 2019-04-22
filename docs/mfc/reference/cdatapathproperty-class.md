---
title: CDataPathProperty Class
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
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780346"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty Class

Uygulayan bir OLE denetim zaman uyumsuz olarak yüklenebilen özelliği.

## <a name="syntax"></a>Sözdizimi

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Oluşturur bir `CDataPathProperty` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDataPathProperty::GetControl](#getcontrol)|İlişkili zaman uyumsuz bir OLE denetimi alır `CDataPathProperty` nesne.|
|[CDataPathProperty::GetPath](#getpath)|Yol özelliğin adını alır.|
|[CDataPathProperty::Open](#open)|İlişkili (OLE) ActiveX denetimi için zaman uyumsuz özelliği yüklenmesini başlatır.|
|[CDataPathProperty::ResetData](#resetdata)|Çağrıları `CAsyncMonikerFile::OnDataAvailable` denetim özelliklerini değiştirmiş kapsayıcı bildirir.|
|[CDataPathProperty::SetControl](#setcontrol)|Özellikle ilişkili zaman uyumsuz (OLE) ActiveX denetimi ayarlar.|
|[CDataPathProperty::SetPath](#setpath)|Özelliğin yol adını ayarlar.|

## <a name="remarks"></a>Açıklamalar

Zaman uyumsuz özellikler, zaman uyumlu başlatma sonra yüklenir.

Sınıf `CDataPathProperty` türetilir `CAysncMonikerFile`. OLE denetimleriniz zaman uyumsuz özellikleri uygulamak için öğesinden bir sınıf türetin `CDataPathProperty`ve geçersiz kılma [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).

Zaman uyumsuz adlar ve ActiveX denetimleri, Internet uygulamalarında kullanma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Internet ilk adımlar: ActiveX denetimleri](../../mfc/activex-controls-on-the-internet.md)

- [Internet ilk adımlar: Zaman uyumsuz adlar](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty

Oluşturur bir `CDataPathProperty` nesne.

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Şununla ilişkili olmasını OLE denetimi nesneye bir işaretçi `CDataPathProperty` nesne.

*lpszPath*<br/>
Mutlak veya göreli olabilir, yolun özelliği gerçek mutlak konumunu başvuran bir zaman uyumsuz bir bilinen ad oluşturmak için kullanılır. `CDataPathProperty` URL değil dosya adlarını kullanır. İsterseniz bir `CDataPathProperty` önüne ekleyin, nesne için bir dosya `file://` yolu.

### <a name="remarks"></a>Açıklamalar

`COleControl` Nesne tarafından işaret edilen *pControl* tarafından kullanılan `Open` ve türetilmiş sınıflar tarafından alınır. Varsa *pControl* null ile kullanılan denetimi `Open` ile ayarlanmalıdır `SetControl`. Varsa *lpszPath* NULL ise yolunda geçirebilirsiniz `Open` veya ile ayarlayın `SetPath`.

##  <a name="getcontrol"></a>  CDataPathProperty::GetControl

Almak için bu üye işlevi çağrısı `COleControl` ilişkili nesne `CDataPathProperty` nesne.

```
COleControl* GetControl();
```

### <a name="return-value"></a>Dönüş Değeri

OLE denetim için bir işaretçi ile ilişkili döndürür `CDataPathProperty` nesne. Denetim değilse NULL ilişkili.

##  <a name="getpath"></a>  CDataPathProperty::GetPath

Yol almak, ne zaman ayarlamak için bu üye işlevini çağırın `CDataPathProperty` nesne oluşturulmuş veya belirtilen `Open`, ya da önceki çağrıda belirtilen `SetPath` üye işlevi.

```
CString GetPath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Özellik için yol adını döndürür. Hiçbir yol belirtilmemiş olması durumunda boş olabilir.

##  <a name="open"></a>  CDataPathProperty::Open

İlişkili denetimi için zaman uyumsuz özelliği yüklenmesini başlatmak için bu üye işlevini çağırın.

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
Şununla ilişkili olmasını OLE denetimi nesneye bir işaretçi `CDataPathProperty` nesne.

*pError*<br/>
Dosya özel durum işaretçisi. Neden bir hata olması durumunda ayarlanması gerekir.

*lpszPath*<br/>
Mutlak veya göreli olabilir, yolun özelliği gerçek mutlak konumunu başvuran bir zaman uyumsuz bir bilinen ad oluşturmak için kullanılır. `CDataPathProperty` URL değil dosya adlarını kullanır. İsterseniz bir `CDataPathProperty` önüne ekleyin, nesne için bir dosya `file://` yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İşlev almaya çalıştığında `IBindHost` denetiminden arabirimi.

Çağırmadan önce `Open` yol olmadan, özelliğin yolu için bir değer ayarlamanız gerekir. Nesne yapılandırılmış, veya çağırarak olduğunda bu yapılabilir `SetPath` üye işlevi.

Çağırmadan önce `Open` bir denetimi olmadan (eski adıyla bir OLE denetim olarak bilinir) bir ActiveX denetimini nesneyle ilişkili olabilir. Nesne yapılandırılmış, veya çağırarak olduğunda bu yapılabilir `SetControl`.

Tüm aşırı yüklemeler, [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) ayrıca kullanılabilir `CDataPathProperty`.

##  <a name="resetdata"></a>  CDataPathProperty::ResetData

Almak için bu işlevi çağırın `CAsyncMonikerFile::OnDataAvailable` kapsayıcı denetimi özellikleri değiştirildi ve zaman uyumsuz olarak yüklenen tüm bilgileri yararlıdır bildirir.

```
virtual void ResetData();
```

### <a name="remarks"></a>Açıklamalar

Açılış yeniden başlatılması gerekir. Türetilmiş sınıfları farklı varsayılan olarak bu işlev geçersiz kılabilirsiniz.

##  <a name="setcontrol"></a>  CDataPathProperty::SetControl

Zaman uyumsuz bir OLE denetimi ile ilişkilendirmek için bu üye işlevi çağrısı `CDataPathProperty` nesne.

```
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>Parametreler

*pControl*<br/>
Zaman uyumsuz OLE denetim özelliği ile ilişkilendirilmesi için bir işaretçi.

##  <a name="setpath"></a>  CDataPathProperty::SetPath

Özelliğin yol ayarlamak için bu üye işlevini çağırın.

```
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>Parametreler

*lpszPath*<br/>
Mutlak veya göreli zaman uyumsuz olarak yüklenen özelliğine olabilen bir yolu. `CDataPathProperty` URL değil dosya adlarını kullanır. İsterseniz bir `CDataPathProperty` önüne ekleyin, nesne için bir dosya `file://` yolu.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örneği görüntüsü](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
