---
title: CMouseManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1788e5f3938cc496e66aa24d6d1b6a37603e7d7b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039953"
---
# <a name="cmousemanager-class"></a>CMouseManager sınıfı
Farklı komutlar belirli bir ile ilişkilendirilecek bir kullanıcının [CView](../../mfc/reference/cview-class.md) kullanıcı bu görünüm içinde tıklattığında nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|Ekler bir `CView` nesnesini **özelleştirme** iletişim kutusu. **Özelleştirme** çift tıklatma bir komutla her listelenen görünümleri için ilişkilendirilecek kullanıcı iletişim kutusu sağlar.|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Kullanıcı sağlanan görünüm içinde tıklattığında çalıştırılan komut döndürür.|  
|[CMouseManager::GetViewIconId](#getviewiconid)|Sağlanan görünüm kimlikle ilişkili simgesini döndürür|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|Belirtilen görünüm adı ile ilişkili görünüm kimliği döndürür.|  
|[CMouseManager::GetViewNames](#getviewnames)|Tüm ek görünüm adlarının bir listesini alır.|  
|[CMouseManager::LoadState](#loadstate)|Yükleri `CMouseManager` Windows kayıt defterinden durum.|  
|[CMouseManager::SaveState](#savestate)|Yazar `CMouseManager` Windows kayıt defterinde durum.|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Sağlanan komut ve sağlanan görünüm ilişkilendirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMouseManager` Sınıfı tutar koleksiyonu `CView` nesneleri. Her görünüm adını ve kimlik tarafından tanımlanan Bu görünümler gösterilir **özelleştirme** iletişim kutusu. Kullanıcının herhangi bir görünüm ile ilişkilendirilen komutu değiştirebilirsiniz **özelleştirme** iletişim kutusu. Kullanıcı Bu görünümde tıklattığında ilişkili komutu yürütülür. Bu kodlama açısından desteklemek için WM_LBUTTONDBLCLK ileti ve çağrı işlem [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) kodu işlevinde `CView` nesne...  
  
 Değil oluşturmalısınız bir `CMouseManager` el ile nesne. Uygulamanızı çerçevesi tarafından oluşturulur. Kullanıcı uygulamayı çıktığında otomatik olarak da yok olacaktır. Uygulamanız için fare Yöneticisi bir işaretçi almak için arama [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmousemanager.h  
  
##  <a name="addview"></a>  CMouseManager::AddView  
 Kayıtları bir [CView](../../mfc/reference/cview-class.md) nesnesi ile [CMouseManager sınıfı](../../mfc/reference/cmousemanager-class.md) özel fare davranışını desteklemez.  
  
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
 [in] *iViewId*  
 Bir görünüm kimliği  
  
 [in] *uiViewNameResId*  
 Görünüm adı başvuruda bulunan bir kaynak dize kimliği.  
  
 [in] *uiIconId*  
 Bir görünümü simgesi kimliği  
  
 [in] *IID*  
 Bir görünüm kimliği  
  
 [in] *lpszViewName*  
 Bir görünüm adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel fare davranışı desteklemek için bir görünümü ile kayıtlı olması gerekir `CMouseManager` nesnesi. Herhangi bir nesne türetilmiş `CView` sınıfı fare Yöneticisi ile kaydedilebilir. Dize ve görünüm ile ilişkilendirilen simgesi görüntülenir **fare** sekmesinde **Özelleştir** iletişim kutusu.  
  
 Oluşturmak ve görünüm kimlikleri gibi korumak için programcı sorumluluğundadır *iViewId* ve *IID*.  
  
 Özel fare davranışı sağlamak nasıl hakkında daha fazla bilgi için bkz: [klavye ve fare özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir işaretçi almak nasıl gösteren bir `CMouseManager` kullanarak nesne `CWinAppEx::GetMouseManager` yöntemi ve `AddView` yönteminde `CMouseManager` sınıfı. Bu kod parçacığını parçası olan [durumu toplama örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand  
 Kullanıcı sağlanan görünüm içinde tıklattığında çalıştırılan komut döndürür.  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *IID*  
 Görünüm kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görünüm bir komut ile ilişkili ise, komut tanımlayıcısı; Aksi takdirde 0.  
  
##  <a name="getviewiconid"></a>  CMouseManager::GetViewIconId  
 Bir görünüm kimliği ile ilişkili simgeyi alır.  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iViewId*  
 Görünüm kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir simge kaynak tanımlayıcısı başarılıysa; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Görünüm ilk kullanılarak kaydedilmemesi şartıyla bu yöntem başarısız olur [CMouseManager::AddView](#addview).  
  
##  <a name="getviewidbyname"></a>  CMouseManager::GetViewIdByName  
 Bir görünüm adı ile ilişkili görünüm kimliği alır.  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszName*  
 Görünüm adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir görünüm kimliği olduğu başarılıysa; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem arar kullanarak kayıtlı görünümleri aracılığıyla [CMouseManager::AddView](#addview).  
  
##  <a name="getviewnames"></a>  CMouseManager::GetViewNames  
 Tüm kayıtlı görünüm adlarının bir listesini alır.  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *listOfNames*  
 Bir başvuru `CStringList` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem parametresi doldurur `listOfNames` kullanarak kayıtlı tüm görünümleri adlarıyla [CMouseManager::AddView](#addview).  
  
##  <a name="loadstate"></a>  CMouseManager::LoadState  
 Durumu yükler [CMouseManager sınıfı](../../mfc/reference/cmousemanager-class.md) kayıt defterinden.  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Bir kayıt defteri anahtarı yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt defterinden yüklenen durum bilgilerini kayıtlı görünümleri, tanımlayıcılarını görüntüle ve ilişkili komutları içerir. Varsa parametresi *lpszProfileName* olan `NULL`, bu işlev yükler `CMouseManager` tarafından denetlenen varsayılan kayıt defteri konumu verilerden [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md).  
  
 Çoğu durumda, bu işlev doğrudan çağırmanız gerekmez. Çalışma alanı başlatma işleminin bir parçası olarak adlandırılır. Çalışma alanı başlatma işlemi hakkında daha fazla bilgi için bkz: [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate).  
  
##  <a name="savestate"></a>  CMouseManager::SaveState  
 Durumu Yazar [CMouseManager sınıfı](../../mfc/reference/cmousemanager-class.md) kayıt defteri.  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszProfileName*  
 Bir kayıt defteri anahtarı yolu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm kayıtlı görünümleri, tanımlayıcılarını görüntüle ve ilişkili komutları kayıt defterine yazılır durum bilgilerini içerir. Varsa parametresi *lpszProfileName* olan `NULL`, bu işlev Yazar `CMouseManager` tarafından denetlenen varsayılan kayıt defteri konumu için veri [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md).  
  
 Çoğu durumda, bu işlev doğrudan çağırmanız gerekmez. Çalışma alanı serileştirme işleminin bir parçası olarak adlandırılır. Çalışma alanı seri hale getirme işlemi hakkında daha fazla bilgi için bkz: [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).  
  
##  <a name="setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk  
 Özel bir komut fare yöneticisiyle önce kaydedilmiş bir görünümü ile ilişkilendirir.  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iViewId*  
 Görünüm tanımlayıcısı.  
  
 [in] *uiCmd*  
 Komut tanımlayıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir komut bir görünümü ile ilişkilendirmek için önce görünümü kullanarak kaydetmeniz gerekir [CMouseManager::AddView](#addview). `AddView` Yöntemi, bir görünüm tanımlayıcı bir giriş parametresi olarak gerektirir. Bir görünüm kaydettiğinizde çağırabilirsiniz `CMouseManager::SetCommandForDblClk` için sağlanan aynı görünüm tanımlayıcı giriş parametresi ile `AddView`. Bundan sonra kullanıcı kayıtlı görünümünde fare tıklattığında uygulama belirtildiği komutu yürütecek *uiCmd.* Özel fare davranışı desteklemek için fare Yöneticisi ile kayıtlı görünümünü özelleştirmek gerekir. Özel fare davranışı hakkında daha fazla bilgi için bkz: [klavye ve fare özelleştirmesi](../keyboard-and-mouse-customization.md).  
  
 Varsa *uiCmd* ayarlanmış 0 olarak belirtilen görünüm artık bir komutla ilişkili değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)   
 [Klavye ve Fare Özelleştirmesi](../../mfc/keyboard-and-mouse-customization.md)



