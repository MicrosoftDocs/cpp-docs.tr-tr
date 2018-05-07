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
ms.openlocfilehash: 590914ac312a4f998eb759beb08ed2e7935874fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl sınıfı
Windows ortak sık kullanılan tuş denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Oluşturan bir `CHotKeyCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Sık kullanılan tuş denetimi oluşturur ve ona ekler bir `CHotKeyCtrl` nesnesi.|  
|[CHotKeyCtrl::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri ile sık kullanılan tuş denetimi oluşturur ve ekler bir `CHotKeyCtrl` nesnesi.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Sanal anahtar kodu ve değiştirici bayraklarını sık kullanılan tuş bir sık kullanılan tuş denetimi alır.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Yerel karakter kümesinde bir kısayol tuşu için atanan anahtar adını alır.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Belirtilen sanal anahtar koduna atanan yerel karakter kümesinde anahtar adını alır.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Sık kullanılan tuş bileşimini sık kullanılan tuş denetimi için ayarlar.|  
|[CHotKeyCtrl::SetRules](#setrules)|Geçersiz birleşimleri ve sık kullanılan tuş denetimi için varsayılan değiştirici birleşimi tanımlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir "Sık kullanılan tuş denetimi" Sık kullanılan tuş oluşturmak kullanıcının sağlayan bir penceredir. "Sık kullanılan tuş" hızlı bir şekilde bir eylemi gerçekleştirmek için kullanıcı basabilirsiniz anahtar bir birleşimidir. (Örneğin, bir kullanıcı belirli bir pencere etkinleştirir ve Z düzenini üst kısmına beraberinde getirir sık kullanılan tuş oluşturabilirsiniz.) Sık kullanılan tuş denetimi kullanıcının seçimlerini görüntüler ve kullanıcının geçerli bir tuş bileşimi seçtiği sağlar.  
  
 Bu denetim (ve bu nedenle `CHotKeyCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Kullanıcının bir tuş bileşimini seçtiği zaman uygulama belirtilen tuş bileşimini denetimden alabilir ve kullanmak **WM_SETHOTKEY** sistemdeki etkin anahtarı oluşturmak için ileti. Her kullanıcının sık kullanılan tuş bundan sonra tüm sistem bölümünden bastığında penceresi belirtilen **WM_SETHOTKEY** ileti alır bir `WM_SYSCOMMAND` iletisini belirten **SC_HOTKEY**. Bu ileti aldığı penceresini etkinleştirir. Adlı uygulama kadar sık kullanılan tuş geçerli kaldığı **WM_SETHOTKEY** çıkar.  
  
 Bu bağımlı etkin anahtar destekten farklı bir mekanizmadır **WM_HOTKEY** ileti ve Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) ve [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) işlevleri.  
  
 Kullanma hakkında daha fazla bilgi için `CHotKeyCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl  
 Oluşturan bir `CHotKeyCtrl` nesnesi.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>  CHotKeyCtrl::Create  
 Sık kullanılan tuş denetimi oluşturur ve ona ekler bir `CHotKeyCtrl` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Sık kullanılan tuş denetimi 's stilini belirtir. Herhangi bir bileşimini denetim stilleri uygulayın. Bkz: [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) daha fazla bilgi için Windows SDK'sındaki.  
  
 `rect`  
 Sık kullanılan tuş denetimi 's boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT yapısı](../../mfc/reference/rect-structure1.md).  
  
 `pParentWnd`  
 Sık kullanılan tuş denetimi ait ana penceresinde, genellikle belirten bir [CDialog](../../mfc/reference/cdialog-class.md). Değil olmalıdır **NULL**.  
  
 `nID`  
 Sık kullanılan tuş denetimi kişinin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan, başlatma başarılı olduysa; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CHotKeyCtrl` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve ardından arama **oluşturma**, sık kullanılan tuş denetimi oluşturur ve ekler `CHotKeyCtrl` nesnesi.  
  
 Genişletilmiş windows stilleri denetimi ile kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine **oluşturma**.  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 Bir denetim (alt pencere) oluşturmak ve bunu ile ilişkilendirmek için bu işlevi çağırmak `CHotKeyCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExStyle`  
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri listesi için bkz: `dwExStyle` parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `dwStyle`  
 Sık kullanılan tuş denetimi 's stilini belirtir. Herhangi bir bileşimini denetim stilleri uygulayın. Daha fazla bilgi için bkz: [ortak denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775498) Windows SDK.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı `pParentWnd`.  
  
 `pParentWnd`  
 Denetimin üst penceresi için bir işaretçi.  
  
 `nID`  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 Sanal anahtar kodu ve değiştirici bayraklarını bir klavye kısayolu bir sık kullanılan tuş denetimi alır.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `wVirtualKeyCode`  
 Klavye kısayolu sanal anahtar kodu. Standart sanal anahtar kodları listesi için Winuser.h bakın.  
  
 [out] `wModifiers`  
 Bitsel bir birleşimi (veya) klavye kısayolu değiştirici tuşları belirten bayrak.  
  
 Değiştirici bayrakları aşağıdaki gibidir:  
  
|Bayrağı|Karşılık gelen anahtarı|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT tuşu|  
|`HOTKEYF_CONTROL`|CTRL tuşunu|  
|`HOTKEYF_EXT`|Genişletilmiş Anahtar|  
|`HOTKEYF_SHIFT`|SHIFT tuşunu|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk yöntem, aşırı yüklenmiş bir `DWORD` , sanal anahtar kodu ve değiştirici işaretler içerir. Düşük düzey Word düşük düzey bayt sanal anahtar kodu içerir, yüksek sıralı bayt düşük düzey word'ün değiştiricisi bayrakları içerir ve yüksek düzey word sıfır olur.  
  
### <a name="remarks"></a>Açıklamalar  
 Sanal anahtar kodu ve birlikte değiştirici tuşları klavye kısayolu tanımlayın.  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 Sık kullanılan tuş yerelleştirilmiş adını almak için bu üye işlevini çağırın.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şu anda seçili sık kullanılan tuş yerelleştirilmiş adı. Seçili hiçbir sık kullanılan tuş ise `GetHotKeyName` boş bir dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevinin döndürdüğü adı klavye sürücüsünden gelir. Windows, yerelleştirilmiş bir sürümün yerelleştirilmemiş klavye sürücüsünü yükleyebilirsiniz ve tersi.  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 Belirtilen bir sanal anahtar kodu için atanan anahtarı yerelleştirilmiş adını almak için bu üye işlevini çağırın.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Parametreler  
 `vk`  
 Sanal anahtar kodu.  
  
 *fExtended*  
 Sanal anahtar kodu genişletilmiş bir anahtarı ise **TRUE**; Aksi halde **FALSE**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen anahtar yerelleştirilmiş adı `vk` parametresi. Eşlenen adı, anahtar yoksa `GetKeyName` boş bir dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows, yerelleştirilmiş bir sürümün yerelleştirilmemiş klavye sürücüsü yükleyebilmek için bu işlevi döndürür anahtar adı klavye sürücüsünden gelen tersi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 Sık kullanılan tuş denetimi için klavye kısayolu ayarlar.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `wVirtualKeyCode`  
 Klavye kısayolu sanal anahtar kodu. Standart sanal anahtar kodları listesi için Winuser.h bakın.  
  
 [in] `wModifiers`  
 Bitsel bir birleşimi (veya) klavye kısayolu değiştirici tuşları belirten bayrak.  
  
 Değiştirici bayrakları aşağıdaki gibidir:  
  
|Bayrağı|Karşılık gelen anahtarı|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT tuşu|  
|`HOTKEYF_CONTROL`|CTRL tuşunu|  
|`HOTKEYF_EXT`|Genişletilmiş Anahtar|  
|`HOTKEYF_SHIFT`|SHIFT tuşunu|  
  
### <a name="remarks"></a>Açıklamalar  
 Sanal anahtar kodu ve birlikte değiştirici tuşları klavye kısayolu tanımlayın.  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 Geçersiz birleşimleri ve sık kullanılan tuş denetimi için varsayılan değiştirici birleşimi tanımlamak için bu işlevini çağırın.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parametreler  
 `wInvalidComb`  
 Geçersiz tuş bileşimlerini belirler bayrakları dizisi. Bir birleşimi aşağıdaki değerlerden biri olabilir:  
  
- `HKCOMB_A` ALT  
  
- `HKCOMB_C` CTRL  
  
- `HKCOMB_CA` CTRL + ALT  
  
- `HKCOMB_NONE` Değiştirilmemiş anahtarları  
  
- `HKCOMB_S` KAYDIRMA  
  
- `HKCOMB_SA` SHIFT + ALT  
  
- `HKCOMB_SC` SHIFT + CTRL  
  
- `HKCOMB_SCA` SHIFT + CTRL + ALT  
  
 `wModifiers`  
 Kullanıcı geçersiz bir birleşim girdiğinde kullanmak için bir tuş bileşimini belirtir bayrakları dizisi. Değiştirici bayrakları hakkında daha fazla bilgi için bkz: [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı girdiğinde bir geçersiz anahtar birleşimi belirtilen bayrakları tarafından tanımlanan `wInvalidComb`, sistem, belirtilen bayrağı ile kullanıcı tarafından girilen anahtarlarını birleştirmek için veya işlecini kullanır `wModifiers`. Sonuçta elde edilen anahtar birleşimi bir dizeye dönüştürülür ve ardından sık kullanılan tuş denetimi içinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



