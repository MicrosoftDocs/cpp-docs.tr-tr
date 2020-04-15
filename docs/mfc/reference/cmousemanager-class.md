---
title: CMouseManager Sınıfı
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
ms.openlocfilehash: d05a2e186f001a69310e99cec013193a4d1bff3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319730"
---
# <a name="cmousemanager-class"></a>CMouseManager Sınıfı

Kullanıcı bu görünümün içine çift tıkladığında, kullanıcının belirli bir [CView](../../mfc/reference/cview-class.md) nesnesi ile farklı komutları ilişkilendirmesine olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
class CMouseManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMouseManager::AddView](#addview)|**Özelleştirme** `CView` iletişim kutusuna bir nesne ekler. **Özelleştirme** iletişim kutusu, kullanıcının listelenen görünümlerin her biri için bir komutla çift tıklatmayı ilişkilendirmesini sağlar.|
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Kullanıcı sağlanan görünümün içine çift tıkladığında çalıştırılan komutu döndürür.|
|[CMouseManager::GetViewIconid](#getviewiconid)|Sağlanan görünüm kimliğiyle ilişkili simgeyi döndürür.|
|[CMouseManager::Getviewidbyname](#getviewidbyname)|Sağlanan görünüm adı ile ilişkili görünüm kimliğini döndürür.|
|[CMouseManager::GetViewNames](#getviewnames)|Eklenen tüm görünüm adlarının listesini alır.|
|[CMouseManager::LoadState](#loadstate)|`CMouseManager` Durumu Windows kayıt defterinden yükler.|
|[CMouseManager::SaveState](#savestate)|`CMouseManager` Durumu Windows kayıt defterine yazar.|
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Sağlanan komutu ve sağlanan görünümü ilişkilendirer.|

## <a name="remarks"></a>Açıklamalar

Sınıf `CMouseManager` nesnelerin bir koleksiyon `CView` tutar. Her görünüm bir ad ve bir kimlikle tanımlanır. Bu görünümler **Özelleştirme** iletişim kutusunda gösterilir. Kullanıcı, **Özelleştirme** iletişim kutusu aracılığıyla herhangi bir görünümle ilişkili komutu değiştirebilir. Kullanıcı bu görünümde çift tıklatıldığında ilişkili komut yürütülür. Bunu kodlama açısından desteklemek için, WM_LBUTTONDBLCLK mesajını işlemeli ve [cWinAppEx'i aramalısınız::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) işlevi bu `CView` nesnenin kodunda...

Bir `CMouseManager` nesneyi el ile oluşturmamalısınız. Uygulamanızın çerçevesi tarafından oluşturulacaktır. Ayrıca, kullanıcı uygulamadan çıktığında otomatik olarak imha edilecektir. Uygulamanız için fare yöneticisine bir işaretçi almak için [CWinAppEx::GetMouseManager'u](../../mfc/reference/cwinappex-class.md#getmousemanager)arayın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmousemanager.h

## <a name="cmousemanageraddview"></a><a name="addview"></a>CMouseManager::AddView

Özel fare davranışını desteklemek için [CMouseManager Sınıfına](../../mfc/reference/cmousemanager-class.md) bir [CView](../../mfc/reference/cview-class.md) nesnesi kaydeder.

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
[içinde] Bir görünüm kimliği.

*uiViewNameResId*<br/>
[içinde] Görünüm adına başvuran bir kaynak dize kimliği.

*uiIconId*<br/>
[içinde] Görünüm simgesi kimliği.

*ııd*<br/>
[içinde] Bir görünüm kimliği.

*lpszViewName*<br/>
[içinde] Bir görünüm adı.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Özel fare davranışını desteklemek için, nesneye `CMouseManager` bir görünüm kaydedilmelidir. `CView` Sınıftan türetilen herhangi bir nesne fare yöneticisine kaydedilebilir. Görünümle ilişkili dize ve simge, **Özelleştir** iletişim kutusunun **Fare** sekmesinde görüntülenir.

*iViewId* ve *iId*gibi görünüm kimlikleri oluşturmak ve korumak programcının sorumluluğundadır.

Özel fare davranışının nasıl sağlayabileceği hakkında daha fazla bilgi için klavye ve fare özelleştirmesi'ne bakın. [Keyboard and Mouse Customization](../../mfc/keyboard-and-mouse-customization.md)

### <a name="example"></a>Örnek

Aşağıdaki `CMouseManager` örnek, `CWinAppEx::GetMouseManager` `AddView` `CMouseManager` sınıftayöntem ve yöntemi kullanarak bir nesneye bir işaretçi almak için nasıl gösterir. Bu kod parçacığı Devlet Koleksiyonu [örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand

Kullanıcı sağlanan görünümün içine çift tıkladığında çalıştırılan komutu döndürür.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>Parametreler

*ııd*<br/>
[içinde] Görünüm kimliği.

### <a name="return-value"></a>Dönüş Değeri

Görünüm bir komutla ilişkiliyse komut tanımlayıcısı; aksi takdirde 0.

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a>CMouseManager::GetViewIconid

Görünüm kimliğiyle ilişkili simgeyi alır.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>Parametreler

*iViewId*<br/>
[içinde] Görünüm kimliği.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa simge kaynak tanımlayıcısı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Görünüm ilk olarak CMouseManager kullanılarak kaydedilmezse bu yöntem başarısız [olur::AddView](#addview).

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a>CMouseManager::Getviewidbyname

Bir görünüm adı ile ilişkili görünüm kimliğini alır.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
[içinde] Görünüm adı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa görünüm kimliği; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu [yöntem, CMouseManager](#addview)kullanarak kayıtlı görünümler üzerinden arama::AddView .

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a>CMouseManager::GetViewNames

Tüm kayıtlı görünüm adlarının listesini alır.

```
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Parametreler

*listOfNames*<br/>
[çıkış] Nesneye `CStringList` bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, cmousemanager kullanarak kayıtlı tüm görünümlerin adları ile parametre `listOfNames` [doldurur::AddView](#addview).

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a>CMouseManager::LoadState

[CMouseManager Sınıfının](../../mfc/reference/cmousemanager-class.md) durumunu kayıt defterinden yükler.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt defterinden yüklenen durum bilgileri, kayıtlı görünümleri, görüntü tanımlayıcılarını ve ilişkili komutları içerir. *LpszProfileName* parametresi NULL ise, bu `CMouseManager` işlev verileri [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)tarafından kontrol edilen varsayılan kayıt defteri konumundan yükler.

Çoğu durumda, bu işlevi doğrudan aramanız gerekmez. Çalışma alanı başlatma işleminin bir parçası olarak adlandırılır. Çalışma alanı başlatma işlemi hakkında daha fazla bilgi için [Bkz. CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).

## <a name="cmousemanagersavestate"></a><a name="savestate"></a>CMouseManager::SaveState

[CMouseManager Sınıfının](../../mfc/reference/cmousemanager-class.md) durumunu kayıt defterine yazar.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Kayıt defteri anahtarının yolu.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt defterine yazılan durum bilgileri, tüm kayıtlı görünümleri, görüntü tanımlayıcılarını ve ilişkili komutları içerir. Parametre *lpszProfileName* NULL ise, bu `CMouseManager` işlev verileri [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)tarafından kontrol edilen varsayılan kayıt defteri konumuna yazar.

Çoğu durumda, bu işlevi doğrudan aramanız gerekmez. Çalışma alanı serileştirme işleminin bir parçası olarak adlandırılır. Çalışma alanı serileştirme işlemi hakkında daha fazla bilgi için [Bkz. CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk

Özel bir komutu ilk olarak fare yöneticisine kayıtlı bir görünümle ilişkilendirer.

```
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*iViewId*<br/>
[içinde] Görünüm tanımlayıcısı.

*uiCmd*<br/>
[içinde] Komut tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Özel bir komutu bir görünümle ilişkilendirmek için, önce [CMouseManager:AddView'i](#addview)kullanarak görünümü kaydetmeniz gerekir. Yöntem, `AddView` giriş parametresi olarak bir görünüm tanımlayıcısı gerektirir. Bir görünümü kaydettikten sonra, `CMouseManager::SetCommandForDblClk` ''ye sağladığınız aynı görünüm tanımlayıcı giriş parametresi ile `AddView`arayabilirsiniz. Bundan sonra, kullanıcı kayıtlı görünümde fareyi çift tıklattığında, uygulama *uiCmd* tarafından belirtilen komutu çalıştıracaktır. Özel fare davranışını desteklemek için fare yöneticisine kayıtlı görünümü özelleştirmeniz de gerekir. Özel fare davranışı hakkında daha fazla bilgi için [Klavye ve Fare Özelleştirme'ye](../keyboard-and-mouse-customization.md)bakın.

*UiCmd* 0 olarak ayarlanmışsa, belirtilen görünüm artık bir komutla ilişkilendirilmez.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)<br/>
[Klavye ve Fare Özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)
