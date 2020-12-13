---
description: 'Daha fazla bilgi edinin: CMouseManager sınıfı'
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
ms.openlocfilehash: 9816583aa9d05b76f97f1be1487898b5827fbcae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331559"
---
# <a name="cmousemanager-class"></a>CMouseManager sınıfı

Kullanıcı bu görünümün içinde çift tıkladığında farklı komutları belirli bir [CView](../../mfc/reference/cview-class.md) nesnesiyle ilişkilendirmenize olanak tanır.

## <a name="syntax"></a>Syntax

```
class CMouseManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMouseManager:: AddView](#addview)|`CView` **Özelleştirme** iletişim kutusuna bir nesne ekler. **Özelleştirme** iletişim kutusu, kullanıcının listelenen görünümlerin her biri için bir komutla çift tıklama ile ilişkilendirilmesini sağlar.|
|[CMouseManager:: GetViewDblClickCommand](#getviewdblclickcommand)|Kullanıcı, belirtilen görünümün içine çift tıkladığında yürütülen komutu döndürür.|
|[CMouseManager:: Getviewiconıd](#getviewiconid)|Belirtilen Görünüm KIMLIĞIYLE ilişkili simgeyi döndürür.|
|[CMouseManager:: GetViewIdByName](#getviewidbyname)|Belirtilen Görünüm adıyla ilişkili görünüm KIMLIĞINI döndürür.|
|[CMouseManager:: GetViewNames](#getviewnames)|Tüm eklenen görünüm adlarının listesini alır.|
|[CMouseManager:: LoadState](#loadstate)|`CMouseManager`Windows kayıt defterinden durumu yükler.|
|[CMouseManager:: Savemlak](#savestate)|`CMouseManager`Durumu Windows kayıt defterine yazar.|
|[CMouseManager:: SetCommandForDblClk](#setcommandfordblclk)|Belirtilen komutu ve belirtilen görünümü ilişkilendirir.|

## <a name="remarks"></a>Açıklamalar

`CMouseManager`Sınıfı bir nesne koleksiyonunu tutar `CView` . Her görünüm bir ad ve bir KIMLIK tarafından tanımlanır. Bu görünümler **Özelleştirme** iletişim kutusunda gösterilir. Kullanıcı **Özelleştirme** iletişim kutusu aracılığıyla herhangi bir görünümle ilişkili komutu değiştirebilir. İlişkili komut, Kullanıcı bu görünümde çift tıkladığında yürütülür. Bunu bir kodlama perspektifinden desteklemek için WM_LBUTTONDBLCLK iletisini işleyin ve bu nesnenin kodunda [CWinAppEx:: OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) işlevini çağırmanız gerekir `CView` .

`CMouseManager`El ile bir nesne oluşturmamalıdır. Uygulamanızın çerçevesi tarafından oluşturulacaktır. Kullanıcı uygulamadan çıktığında da otomatik olarak yok edilir. Uygulamanızın fare yöneticisine yönelik bir işaretçi almak için, [CWinAppEx:: GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)' ı çağırın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmousemanager. h

## <a name="cmousemanageraddview"></a><a name="addview"></a> CMouseManager:: AddView

Özel fare davranışını desteklemek için [CMouseManager sınıfıyla](../../mfc/reference/cmousemanager-class.md) bir [CView](../../mfc/reference/cview-class.md) nesnesi kaydeder.

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

*ıviewıd*<br/>
'ndaki Bir görünüm KIMLIĞI.

*Uıviewnameresıd*<br/>
'ndaki Görünüm adına başvuran bir kaynak dizesi KIMLIĞI.

*Uıiconıd*<br/>
'ndaki Bir görünüm simgesi KIMLIĞI.

*'Si*<br/>
'ndaki Bir görünüm KIMLIĞI.

*lpszViewName*<br/>
'ndaki Bir görünüm adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel fare davranışını desteklemek için, nesneyle birlikte bir görünüm kaydedilmesi gerekir `CMouseManager` . Sınıfından türetilmiş herhangi bir nesne, `CView` Fare Yöneticisi ile kaydedilebilir. Bir görünümle ilişkili dize ve simge, **Özelleştir** Iletişim kutusunun **fare** sekmesinde görüntülenir.

Bu, programcının *ıviewıd* ve *IID* gibi görünüm kimliklerini oluşturma ve sürdürme sorumluluğunun sorumluluğundadır.

Özel fare davranışı sağlama hakkında daha fazla bilgi için bkz. [klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yöntemi ve yöntemi kullanılarak nesnesine bir işaretçinin nasıl alınacağını gösterir `CMouseManager` `CWinAppEx::GetMouseManager` `AddView` `CMouseManager` . Bu kod parçacığı, [durum toplama örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a> CMouseManager:: GetViewDblClickCommand

Kullanıcı, belirtilen görünümün içine çift tıkladığında yürütülen komutu döndürür.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>Parametreler

*'Si*<br/>
'ndaki Görünüm KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Görünüm bir komutla ilişkiliyse, komut tanımlayıcısı; Aksi takdirde 0.

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a> CMouseManager:: Getviewiconıd

Bir görünüm KIMLIĞIYLE ilişkili simgeyi alır.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>Parametreler

*ıviewıd*<br/>
'ndaki Görünüm KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir simge kaynak tanımlayıcısı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, görünüm ilk olarak [CMouseManager:: AddView](#addview)kullanılarak kaydedilmemişse başarısız olur.

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a> CMouseManager:: GetViewIdByName

Bir görünüm adı ile ilişkili görünüm KIMLIĞINI alır.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
'ndaki Görünüm adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa bir görünüm KIMLIĞI; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CMouseManager:: AddView](#addview)kullanılarak kaydedilen görünümlerde arama yapar.

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a> CMouseManager:: GetViewNames

Tüm kayıtlı görünüm adlarının listesini alır.

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametreler

*Lıfnames*<br/>
dışı Nesnesine bir başvuru `CStringList` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `listOfNames` [CMouseManager:: AddView](#addview)kullanılarak kaydedilen tüm görünümlerin adlarıyla parametresini doldurur.

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a> CMouseManager:: LoadState

[CMouseManager sınıfının](../../mfc/reference/cmousemanager-class.md) durumunu kayıt defterinden yükler.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt defterinden yüklenen durum bilgileri, kayıtlı görünümleri, görünüm tanımlayıcılarını ve ilişkili komutları içerir. *LpszProfileName* parametresi null ise, bu Işlev `CMouseManager` [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)tarafından denetlenen varsayılan kayıt defteri konumundaki verileri yükler.

Çoğu durumda, bu işlevi doğrudan çağırmanız gerekmez. Çalışma alanı başlatma sürecinin bir parçası olarak çağrılır. Çalışma alanı başlatma işlemi hakkında daha fazla bilgi için bkz. [CWinAppEx:: LoadState](../../mfc/reference/cwinappex-class.md#loadstate).

## <a name="cmousemanagersavestate"></a><a name="savestate"></a> CMouseManager:: Savemlak

[CMouseManager sınıfının](../../mfc/reference/cmousemanager-class.md) durumunu kayıt defterine yazar.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt defterine yazılan durum bilgileri, tüm kayıtlı görünümleri, görünüm tanımlayıcılarını ve ilişkili komutları içerir. *LpszProfileName* parametresi null ise, bu Işlev `CMouseManager` verileri [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)tarafından denetlenen varsayılan kayıt defteri konumuna yazar.

Çoğu durumda, bu işlevi doğrudan çağırmanız gerekmez. Çalışma alanı serileştirme sürecinin bir parçası olarak çağrılır. Çalışma alanı serileştirme işlemi hakkında daha fazla bilgi için bkz. [CWinAppEx:: Savemlak](../../mfc/reference/cwinappex-class.md#savestate).

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a> CMouseManager:: SetCommandForDblClk

Özel bir komutu, fare Yöneticisi ile ilk kaydedilen bir görünümle ilişkilendirir.

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*ıviewıd*<br/>
'ndaki Görünüm tanımlayıcısı.

*Uımd*<br/>
'ndaki Komut tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Özel bir komutu bir görünümle ilişkilendirmek için, önce [CMouseManager:: AddView](#addview)kullanarak görünümü kaydetmeniz gerekir. `AddView`Yöntemi, giriş parametresi olarak bir görünüm tanımlayıcısı gerektirir. Bir görünümü kaydettiğinizde, `CMouseManager::SetCommandForDblClk` için sağladığınız aynı görünüm tanımlayıcı giriş parametresiyle birlikte çağırabilirsiniz `AddView` . Bundan sonra, Kullanıcı kayıtlı görünümde fareyi çift tıkladığında, uygulama *Uııcmd* tarafından belirtilen komutu yürütür. Özel fare davranışını desteklemek için, ayrıca fare Yöneticisi ile kaydedilmiş görünümü özelleştirmeniz gerekir. Özel fare davranışları hakkında daha fazla bilgi için bkz. [klavye ve fare özelleştirmesi](../keyboard-and-mouse-customization.md).

*Uııcmd* 0 olarak ayarlandıysa, belirtilen görünüm artık bir komutla ilişkilendirilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[Klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)
