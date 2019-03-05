---
title: CMouseManager sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: d58293b94eeaf499c48f750972b15256e9c19794
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293192"
---
# <a name="cmousemanager-class"></a>CMouseManager sınıfı

Bir kullanıcının farklı komutları belirli bir ile ilişkilendirilecek sağlar [CView](../../mfc/reference/cview-class.md) kullanıcı söz konusu görünümü çift tıkladığında nesne.

## <a name="syntax"></a>Sözdizimi

```
class CMouseManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMouseManager::AddView](#addview)|Ekler bir `CView` nesnesini **özelleştirme** iletişim kutusu. **Özelleştirme** çift bir komutla her listelenen görünümleri için ilişkilendirilecek kullanıcı iletişim kutusu sağlar.|
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Kullanıcının sağlanan görünümü çift tıkladığında çalıştırılan komut döndürür.|
|[CMouseManager::GetViewIconId](#getviewiconid)|Belirtilen görünüm kimliği ile ilişkili simgeyi döndürür|
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Belirtilen görünüm adı ile ilişkili görünüm kimliği döndürür.|
|[CMouseManager::GetViewNames](#getviewnames)|Tüm eklenen görünüm adlarının bir listesini alır.|
|[CMouseManager::LoadState](#loadstate)|Yükleri `CMouseManager` Windows kayıt defterinden durumu.|
|[CMouseManager::SaveState](#savestate)|Yazar `CMouseManager` Windows kayıt defterine durum.|
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Sağlanan komut ve sağlanan görünümü ilişkilendirir.|

## <a name="remarks"></a>Açıklamalar

`CMouseManager` Sınıfı bir koleksiyonunu tutar `CView` nesneleri. Her görünüm, bir ad ve bir kimliği tarafından tanımlanır. Bu görünümler gösterilir **özelleştirme** iletişim kutusu. Kullanıcının herhangi bir görünüm ilişkili komut değiştirip **özelleştirme** iletişim kutusu. Bu görünümde kullanıcı çift tıkladığında ilgili komutu yürütülür. Bu kodlama açısından desteklemek için çağrı ve WM_LBUTTONDBLCLK ileti işlem [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) kodu işlevinde `CView` nesne...

Oluşturacağınız değil bir `CMouseManager` el ile nesne. Uygulamanızın framework tarafından oluşturulur. Kullanıcı uygulamayı çıktığında otomatik olarak de yok edilir. Bir işaretçi, uygulamanız için fare Manager'a almak için arama [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmousemanager.h

##  <a name="addview"></a>  CMouseManager::AddView

Kayıtları bir [CView](../../mfc/reference/cview-class.md) nesnesi ile [CMouseManager sınıfı](../../mfc/reference/cmousemanager-class.md) özel fare davranışı desteklemek için.

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>Parametreler

*iViewId*<br/>
[in] Görünüm kimliği.

*uiViewNameResId*<br/>
[in] Görünüm adı başvuran kaynak dize kimliği.

*uiIconId*<br/>
[in] Bir görünümü simgesi kimliği

*IID*<br/>
[in] Görünüm kimliği.

*lpszViewName*<br/>
[in] Bir görünüm adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Özel fare davranışı desteklemek için bir görünüm ile kaydedilmelidir `CMouseManager` nesne. Herhangi bir nesne öğesinden türetilen `CView` sınıfı fare yöneticisiyle kaydedilebilir. Bir görünümü ile ilişkili simge ve dize görüntülenen **fare** sekmesinde **Özelleştir** iletişim kutusu.

Oluşturma ve görüntüleme kimlikleri gibi koruma programcının sorumluluğundadır *iViewId* ve *IID*.

Özel fare davranışı sağlama hakkında daha fazla bilgi için bkz. [klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir işaretçi almak gösterilmiştir bir `CMouseManager` kullanarak nesne `CWinAppEx::GetMouseManager` yöntemi ve `AddView` yönteminde `CMouseManager` sınıfı. Bu kod parçacığı parçasıdır [durumu toplama örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

##  <a name="getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand

Kullanıcının sağlanan görünümü çift tıkladığında çalıştırılan komut döndürür.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>Parametreler

*IID*<br/>
[in] Görünüm kimliği.

### <a name="return-value"></a>Dönüş Değeri

Görünüm bir komut ile ilişkili ise, komut tanımlayıcısı; Aksi durumda 0.

##  <a name="getviewiconid"></a>  CMouseManager::GetViewIconId

Bir görünüm kimliği ile ilişkili simgeyi alır.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>Parametreler

*iViewId*<br/>
[in] Görünüm kimliği.

### <a name="return-value"></a>Dönüş Değeri

Simge kaynak tanımlayıcı başarılıysa; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Görünüm ilk kullanarak kayıtlı değilse başarısız olur [CMouseManager::AddView](#addview).

##  <a name="getviewidbyname"></a>  CMouseManager::GetViewIdByName

Bir görünüm adı ile ilişkili görünüm kimliği alır.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
[in] Görünüm adı.

### <a name="return-value"></a>Dönüş Değeri

Bir görünüm kimliği olduğu başarılıysa; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem arar üzerinden görünümlerini kullanarak kayıtlı [CMouseManager::AddView](#addview).

##  <a name="getviewnames"></a>  CMouseManager::GetViewNames

Tüm kayıtlı görünüm adlarının bir listesini alır.

```
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametreler

*listOfNames*<br/>
[out] Bir başvuru `CStringList` nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem parametre doldurur `listOfNames` kullanarak kayıtlı tüm görünümlere adlarıyla [CMouseManager::AddView](#addview).

##  <a name="loadstate"></a>  CMouseManager::LoadState

Durumunu yükler [CMouseManager sınıfı](../../mfc/reference/cmousemanager-class.md) kayıt.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Bir kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Durum bilgileri kayıt defterinden yüklü, kayıtlı görünümler, tanımlayıcılarını görüntüle ve ilişkili komutlar içerir. Parametre *lpszProfileName* NULL ise bu işlev yükler `CMouseManager` tarafından denetlenen varsayılan kayıt defteri konumu verilerden [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md).

Çoğu durumda, doğrudan bu işlevi çağırmanız gerekmez. Çalışma alanı başlatma işleminin bir parçası olarak adlandırılır. Çalışma alanı başlatma işlemi hakkında daha fazla bilgi için bkz: [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).

##  <a name="savestate"></a>  CMouseManager::SaveState

Durumu Yazar [CMouseManager sınıfı](../../mfc/reference/cmousemanager-class.md) kayıt.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Bir kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kayıt defterine yazılan durum bilgileri, tüm kayıtlı görünümler, tanımlayıcılarını görüntüle ve ilişkili komutlar içerir. Parametre *lpszProfileName* yazar bu işlev NULL ise `CMouseManager` veri tarafından denetlenen varsayılan kayıt defteri konumuna [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md).

Çoğu durumda, doğrudan bu işlevi çağırmanız gerekmez. Çalışma alanı seri hale getirme işleminin bir parçası olarak adlandırılır. Çalışma alanı seri hale getirme işlemi hakkında daha fazla bilgi için bkz: [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

##  <a name="setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk

Özel komut ilk fare Manager'a kayıtlı bir görünümü ile ilişkilendirir.

```
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*iViewId*<br/>
[in] Görüntüleme tanımlayıcısı.

*uiCmd*<br/>
[in] Komut tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Özel komut bir görünümü ile ilişkilendirmek için önce görünümü kullanarak kaydetmeniz gerekir [CMouseManager::AddView](#addview). `AddView` Yöntemi giriş parametresi olarak bir görünümü tanımlayıcı gerektirir. Bir görünüm kaydolduğunuzda çağırabilirsiniz `CMouseManager::SetCommandForDblClk` temin ettiğiniz aynı görünümü tanımlayıcı giriş parametresi ile `AddView`. Bundan sonra kullanıcı kayıtlı görünümünde fare çift tıkladığında, uygulama tarafından belirtilen komut yürütülür *uiCmd.* Özel fare davranışı desteklemek için fare Manager'a kayıtlı görünümünü özelleştirmek gerekir. Özel fare davranışı hakkında daha fazla bilgi için bkz: [klavye ve fare özelleştirmesi](../keyboard-and-mouse-customization.md).

Varsa *uiCmd* ayarlanmış 0 olarak belirtilen görünümü artık bir komut ile ilişkili değil.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[Klavye ve Fare Özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)
