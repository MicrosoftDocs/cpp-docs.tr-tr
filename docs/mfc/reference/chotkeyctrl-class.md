---
title: CHotKeyCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8151b69b92566f45766c4ffa25d40bb5f077c606
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337264"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl sınıfı
Windows ortak kısayol denetimi işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Oluşturur bir `CHotKeyCtrl` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Bir sık kullanılan tuş denetimi oluşturur ve ona bağlanan bir `CHotKeyCtrl` nesne.|  
|[CHotKeyCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir sık kullanılan tuş denetimi oluşturur ve ona ekler bir `CHotKeyCtrl` nesne.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Sanal anahtar kod ve değiştirici bayrakları bir kısayol tuşu, bir kısayol tuşu denetimini alır.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Sık kullanılan tuş için atanmış yerel karakter kümesindeki anahtar adını alır.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Belirtilen sanal anahtar koda atanmış yerel karakter kümesindeki anahtar adını alır.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Kısayol tuş bileşimi bir sık kullanılan tuş denetimi için ayarlar.|  
|[CHotKeyCtrl::SetRules](#setrules)|Geçersiz birleşimleri ve varsayılan değiştirici bileşimi için bir kısayol tuşu denetimini tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir "Sık kullanılan tuş denetimi" Sık erişimli bir anahtar oluşturmak kullanıcının sağlayan bir penceredir. "Sık kullanılan tuş" hızlı bir eylem gerçekleştirmek için kullanıcı basabilirsiniz anahtar bir birleşimidir. (Örneğin, bir kullanıcı belirli bir pencereyi etkinleştirir ve Z düzenini üstüne getiren bir kısayol tuşu oluşturabilirsiniz.) Sık kullanılan tuş denetimi, kullanıcının seçimlerini görüntüler ve kullanıcının geçerli bir tuş bileşimi seçmesini sağlar.  
  
 Bu denetimi (ve bu nedenle `CHotKeyCtrl` sınıfı) ve üzeri yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programlar için kullanılabilir.  
  
 Bir tuş bileşimi kullanıcının seçtiği zaman uygulama belirtilen tuş bileşimi denetiminden almak ve WM_SETHOTKEY ileti sistemde etkin anahtar ayarlamak için kullanın. Her kullanıcının kısayol tuşu bundan sonra sistemin herhangi bir bölümünden bastığında WM_SETHOTKEY iletisinde belirtilen pencere SC_HOTKEY belirten bir WM_SYSCOMMAND iletisini alır. Bu iletiyi aldıktan sonra pencereyi etkinleştirir. Kısayol tuşu WM_SETHOTKEY çıkar çağıran uygulama kadar geçerli kalır.  
  
 Bu mekanizma WM_HOTKEY ileti ve Windows bağlıdır etkin anahtar desteği farklıdır [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) ve [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) işlevleri.  
  
 Kullanma hakkında daha fazla bilgi için `CHotKeyCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl  
 Oluşturur bir `CHotKeyCtrl` nesne.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>  CHotKeyCtrl::Create  
 Bir sık kullanılan tuş denetimi oluşturur ve ona bağlanan bir `CHotKeyCtrl` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Sık erişimli anahtar denetiminin stilini belirtir. Denetim stilleri herhangi bir bileşimini uygulayın. Bkz: [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) daha fazla bilgi için Windows SDK.  
  
 *Rect*  
 Sık erişimli anahtar denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT yapısı](../../mfc/reference/rect-structure1.md).  
  
 *pParentWnd*  
 Sık erişimli anahtar denetiminin üst penceresine, genellikle belirtir bir [CDialog](../../mfc/reference/cdialog-class.md). NULL olmamalıdır.  
  
 *nID*  
 Sık erişimli anahtar denetimin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır başlatma başarılı olduysa; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CHotKeyCtrl` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, sık kullanılan tuş denetimi oluşturur ve ona ekler `CHotKeyCtrl` nesne.  
  
 Genişletilmiş windows stilleri ile denetiminizi kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine `Create`.  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 Bir denetim (alt pencere) oluşturma ve ilişkilendirmek için bu işlevi çağırın `CHotKeyCtrl` nesne.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwExStyle*  
 Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK.  
  
 *dwStyle*  
 Sık erişimli anahtar denetiminin stilini belirtir. Denetim stilleri herhangi bir bileşimini uygulayın. Daha fazla bilgi için [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) Windows SDK.  
  
 *Rect*  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.  
  
 *pParentWnd*  
 Denetimin ana penceresine bir işaretçi.  
  
 *nID*  
 Denetimin alt penceresi kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [Oluştur](#create) Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 Sanal anahtar kod ve değiştirici bayrakları klavye kısayolunun bir kısayol tuşu denetimini alır.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *wVirtualKeyCode*  
 Klavye kısayolunu sanal anahtar kodu. Winuser.h standart sanal anahtar kodlarının listesi için bkz.  
  
 [out] *wModifiers*  
 Bitsel bir birleşimi (veya) değiştirici tuşları, klavye kısayolunu gösteren bayrak.  
  
 Değiştirici bayrakları aşağıdaki gibidir:  
  
|Bayrağı|Karşılık gelen anahtar|  
|----------|-----------------------|  
|HOTKEYF_ALT|ALT tuşu|  
|HOTKEYF_CONTROL|CTRL tuşunu|  
|HOTKEYF_EXT|Genişletilmiş Anahtar|  
|HOTKEYF_SHIFT|Shift tuşunu|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk aşırı yüklenmiş yöntem, sanal anahtar kod ve değiştirici bayrakları içeren bir DWORD. Düşük düzey word'ün son bayt sanal tuş kodunu içeren, düşük düzey word'ün yüksek düzeyli bayt değiştirici bayrakları içeriyor ve dwpoint sıfırdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Sanal anahtar kod ve birlikte değiştirici tuşları klavye kısayolunu tanımlayın.  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 Kısayol tuşu yerelleştirilmiş adını almak için bu üye işlevini çağırın.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili kısayol tuşu yerelleştirilmiş adı. Seçili hiçbir kısayol tuşu ise `GetHotKeyName` boş bir dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevinin döndürdüğü adı klavye sürücüsünden gelir. Windows, yerelleştirilmiş bir sürümünde bir klavye yerelleştirilmemiş sürücüsünü yükleyebilirsiniz ve bunun tersi de geçerlidir.  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 Belirtilen sanal anahtar kod atanan anahtarı yerelleştirilmiş adını almak için bu üye işlevini çağırın.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Parametreler  
 *vk*  
 Sanal anahtar kodu.  
  
 *fExtended*  
 Sanal anahtar kodu bir genişletilmiş anahtar TRUE ise; Aksi durumda FALSE.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yerelleştirilmiş adı tarafından belirtilen anahtarın *vk* parametresi. Anahtar eşlenen adı, yoksa `GetKeyName` boş bir dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev döndüren anahtar adı klavye sürücüsünden sunulur; böylece bir klavye yerelleştirilmemiş sürücü Windows, yerelleştirilmiş bir sürümünü yükleyebilirsiniz ve bunun tersi de geçerlidir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 Bir sık kullanılan tuş denetimi için klavye kısayolunu ayarlar.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *wVirtualKeyCode*  
 Klavye kısayolunu sanal anahtar kodu. Winuser.h standart sanal anahtar kodlarının listesi için bkz.  
  
 [in] *wModifiers*  
 Bitsel bir birleşimi (veya) değiştirici tuşları, klavye kısayolunu gösteren bayrak.  
  
 Değiştirici bayrakları aşağıdaki gibidir:  
  
|Bayrağı|Karşılık gelen anahtar|  
|----------|-----------------------|  
|HOTKEYF_ALT|ALT tuşu|  
|HOTKEYF_CONTROL|CTRL tuşunu|  
|HOTKEYF_EXT|Genişletilmiş Anahtar|  
|HOTKEYF_SHIFT|Shift tuşunu|  
  
### <a name="remarks"></a>Açıklamalar  
 Sanal anahtar kod ve birlikte değiştirici tuşları klavye kısayolunu tanımlayın.  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 Geçersiz birleşimleri ve varsayılan değiştirici bileşimi için bir kısayol tuşu denetimini tanımlamak için bu işlevi çağırın.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parametreler  
 *wInvalidComb*  
 Geçersiz anahtar belirten bayrakları dizisi. Bu, aşağıdaki değerleri birleşimi olabilir:  
  
- HKCOMB_A ALT  
  
- HKCOMB_C CTRL  
  
- HKCOMB_CA CTRL + ALT  
  
- HKCOMB_NONE değiştirilmemiş anahtarları  
  
- HKCOMB_S KAYDIRMA  
  
- HKCOMB_SA SHIFT + ALT  
  
- HKCOMB_SC SHIFT + CTRL  
  
- HKCOMB_SCA SHIFT + CTRL + ALT  
  
 *wModifiers*  
 Kullanıcı obsahuje neplatnou kombinaci girdiğinde kullanmak için bir tuş bileşimini belirtir bayrakları dizisi. Değiştirici bayrakları hakkında daha fazla bilgi için bkz. [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı girdiğinde geçersiz bir tuş bileşimi belirtilen bayraklar tarafından tanımlandığı gibi *wInvalidComb*, sistem, belirtilen bayrağı ile kullanıcı tarafından girilen anahtarları birleştirmek için veya işlecini kullanır. *wModifiers*. Elde edilen tuş bileşimi bir dizeye dönüştürülür ve ardından sık kullanılan tuş denetimi içinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



