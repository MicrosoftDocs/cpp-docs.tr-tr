---
title: "CButton sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
dev_langs: C++
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5eb955843d2390864a7fbc2c45025dca39ce498b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cbutton-class"></a>CButton sınıfı
Windows düğme denetimleri işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CButton : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CButton::CButton](#cbutton)|Oluşturan bir `CButton` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CButton::Create](#create)|Windows düğme denetimi oluşturur ve ona ekler `CButton` nesnesi.|  
|[CButton::DrawItem](#drawitem)|Bir sahip tarafından çizilmiş çizmek için geçersiz kılma `CButton` nesnesi.|  
|[CButton::GetBitmap](#getbitmap)|İle önceden ayarlanmış bit eşlem işleyicisini alır [SetBitmap](#setbitmap).|  
|[CButton::GetButtonStyle](#getbuttonstyle)|Düğme denetimi stili ilgili bilgileri alır.|  
|[CButton::GetCheck](#getcheck)|Düğme denetimi onay durumunu alır.|  
|[CButton::GetCursor](#getcursor)|İmleç görüntü tanıtıcısı önceden ayarlanmış ile alır [SetCursor](#setcursor).|  
|[CButton::GetIcon](#geticon)|İle önceden ayarlanmış simgesi işleyicisini alır [SetIcon](#seticon).|  
|[CButton::GetIdealSize](#getidealsize)|Düğme denetimi ideal boyutunu alır.|  
|[CButton::GetImageList](#getimagelist)|Düğme denetimi görüntü listesini alır.|  
|[CButton::GetNote](#getnote)|Geçerli komut bağlantı denetimi Not bileşeninin alır.|  
|[CButton::GetNoteLength](#getnotelength)|Geçerli komut bağlantı denetimi Not metnin uzunluğunu alır.|  
|[CButton::GetSplitGlyph](#getsplitglyph)|Geçerli Bölünmüş düğme denetimi ile ilişkilendirilmiş karakteri alır.|  
|[CButton::GetSplitImageList](#getsplitimagelist)|Geçerli Bölünmüş düğme denetimi için resim listesi alır.|  
|[CButton::GetSplitInfo](#getsplitinfo)|Geçerli Bölünmüş düğme denetim tanımlayan bilgileri alır.|  
|[CButton::GetSplitSize](#getsplitsize)|Geçerli Bölünmüş düğme denetim açılan bileşeninin sınırlayıcı dikdörtgenini alır.|  
|[CButton::GetSplitStyle](#getsplitstyle)|Geçerli bir Bölünmüş düğme denetim tanımlayın Bölünmüş düğme stilleri alır.|  
|[CButton::GetState](#getstate)|Onay durumu, Vurgu durumunu ve bir düğme denetimi odağı durumunu alır.|  
|[CButton::GetTextMargin](#gettextmargin)|Düğme denetiminin metin kenar alır.|  
|[CButton::SetBitmap](#setbitmap)|Düğmeyi görüntülenecek bir bit eşlem belirtir.|  
|[CButton::SetButtonStyle](#setbuttonstyle)|Bir düğme stilini değiştirir.|  
|[CButton::SetCheck](#setcheck)|Düğme denetimi onay durumunu ayarlar.|  
|[CButton::SetCursor](#setcursor)|Düğmeyi görüntülenecek imleç görüntü belirtir.|  
|[CButton::SetDropDownState](#setdropdownstate)|Geçerli Bölünmüş düğme denetim açılan durumunu ayarlar.|  
|[CButton::SetIcon](#seticon)|Düğmeyi görüntülenecek bir simge belirtir.|  
|[CButton::SetImageList](#setimagelist)|Düğme denetimi görüntü listesi ayarlar.|  
|[CButton::SetNote](#setnote)|Not geçerli komut bağlantı denetimini ayarlar.|  
|[CButton::SetSplitGlyph](#setsplitglyph)|Belirtilen bir karakterin geçerli Bölünmüş düğme denetimi ile ilişkilendirir.|  
|[CButton::SetSplitImageList](#setsplitimagelist)|Görüntü listesi geçerli Bölünmüş düğme denetimi ile ilişkilendirir.|  
|[CButton::SetSplitInfo](#setsplitinfo)|Geçerli Bölünmüş düğme denetim tanımlayan bilgileri belirtir.|  
|[CButton::SetSplitSize](#setsplitsize)|Geçerli Bölünmüş düğme denetim açılan bileşeninin sınırlayıcı dikdörtgenini ayarlar.|  
|[CButton::SetSplitStyle](#setsplitstyle)|Geçerli Bölünmüş düğme denetim stilini ayarlar.|  
|[CButton::SetState](#setstate)|Düğme denetimi vurgulama durumunu ayarlar.|  
|[CButton::SetTextMargin](#settextmargin)|Düğme denetiminin metin kenar boşluğu ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Düğme denetimi açma ve kapatma tıklanabilir bir küçük, dikdörtgen alt penceredir. Düğmeleri tek başına ya da grupları ve ya da etiketli veya kullanılabilir olmayan metinle görüntülenir. Kullanıcı tıklattığında bir düğme genellikle görünümünü değiştirir.  
  
 Tipik düğmeler, onay kutusu, radyo düğmesi ve basma düğmesi bulunur. A `CButton` nesne bunlardan birine dönüşebilir göre [button style](../../mfc/reference/styles-used-by-mfc.md#button-styles) tarafından başlatma sırasında belirtilen [oluşturma](#create) üye işlevi.  
  
 Ayrıca, [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) türetilmiş sınıf `CButton` metin yerine bitmap görüntülerle etiketli düğmesi denetimleri oluşturmayı destekler. A `CBitmapButton` bir düğme kullanıcının, aşağı, odaklı ve devre durumları için ayrı bit eşlemler olabilir.  
  
 Düğme denetimi, bir iletişim şablonunu ya da kodunuzdaki doğrudan oluşturabilirsiniz. Her iki durumda da ilk Oluşturucusu çağrısı `CButton` oluşturmak için `CButton` nesne; ardından çağıran **oluşturma** Windows oluşturmak için üye işlevi düğme denetim ve ekleyebilir `CButton` nesne.  
  
 Yapım tek adımlı işlem türetilen bir sınıfta olabilir `CButton`. Çağrı ve türetilmiş sınıf oluşturucu yazma **oluşturma** gelen oluşturucusu içinde.  
  
 Düğme denetimi tarafından kendi üst gönderilen Windows bildirim iletilerini işlemek istiyorsanız (öğesinden türetilmiş bir sınıf genellikle [CDialog](../../mfc/reference/cdialog-class.md)), her ileti için üst sınıfı için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleme.  
  
 Her ileti eşleme girişi aşağıdaki biçimdedir:  
  
 **ON_**bildirim **(**`id`, `memberFxn` **)**  
  
 Burada `id` bildirim göndererek denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazılmış üst üye işlevi adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 Olası ileti eşleme girdileri aşağıdaki gibidir:  
  
|Eşleme girişi|Ne zaman üst öğeye gönderilen...|  
|---------------|----------------------------|  
|**ON_BN_CLICKED**|Kullanıcı bir düğmesine tıklar.|  
|**ON_BN_DOUBLECLICKED**|Kullanıcı bir düğme çift tıklamalar.|  
  
 Oluşturursanız, bir `CButton` bir iletişim kutusu kaynağı nesnesinden `CButton` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CButton` nesne bir pencerede, destroy gerekebilir. Oluşturursanız, `CButton` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** kullanıcı Windows kapandığında yok etmek için bir nesne üzerinde düğmesi. Oluşturursanız, `CButton` üst iletişim nesnesinde katıştırılmış yığını ya da bu nesne, otomatik olarak yok.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cbutton"></a>CButton::CButton  
 Oluşturan bir `CButton` nesnesi.  
  
```  
CButton();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]  
  
##  <a name="create"></a>CButton::Create  
 Windows düğme denetimi oluşturur ve ona ekler `CButton` nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszCaption`  
 Düğme denetimi metnini belirtir.  
  
 `dwStyle`  
 Düğme denetiminin stilini belirtir. Herhangi bir bileşimini uygulamak [düğme stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles) düğmesine.  
  
 `rect`  
 Düğme denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.  
  
 `pParentWnd`  
 Düğme denetiminin ana penceresinde, genellikle belirten bir `CDialog`. Değil olmalıdır **NULL**.  
  
 `nID`  
 Düğme denetiminin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CButton` iki adımda nesne. İlk olarak, Oluşturucusu arayın ve ardından arama **oluşturma**, hangi Windows düğme denetimi oluşturur ve ekler `CButton` nesnesi.  
  
 Varsa **ws_vısıble** stili verilen, Windows düğme denetimi etkinleştirmek ve Göster düğmesi için gerekli tüm iletileri gönderir.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) düğme denetimi için:  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
- **WS_GROUP** grup denetimleri için  
  
- **WS_TABSTOP** sekme sırasını düğmesi eklemek için  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]  
  
##  <a name="drawitem"></a>CButton::DrawItem  
 Sahip tarafından çizilmiş düğmenin görsel yönü değiştiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Uzun bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) yapısı. Yapısı çizilecek madde ve gerekli çizim türü hakkındaki bilgileri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Sahip tarafından çizilmiş düğmesi bulunur **BS_OWNERDRAW** stil kümesi. Bir sahip tarafından çizilmiş için çizim uygulamak için bu üye işlevi geçersiz kılma `CButton` nesnesi. Tüm grafik cihaz arabirimi (GDI) nesneleri görüntüleme bağlamı içinde sağlanan için seçilen uygulama kurtarmalısınız `lpDrawItemStruct` önce üye fonksiyonu sonlandırır.  
  
 Ayrıca bkz. [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]  
  
##  <a name="getbitmap"></a>CButton::GetBitmap  
 İle önceden ayarlanmış bir bit eşlem tanıtıcısı almak için bu üye işlevini çağırın [SetBitmap](#setbitmap), yani ilişkili bir düğme.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir bit eşlem için bir tanıtıcı. **NULL** hiçbir bit eşlem daha önce belirtildiği takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="getbuttonstyle"></a>CButton::GetButtonStyle  
 Düğme denetimi stili ilgili bilgileri alır.  
  
```  
UINT GetButtonStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu düğme stilleri döndürür `CButton` nesnesi. Bu işlev yalnızca döndürür [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stili değerleri, herhangi bir pencere stilleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="getcheck"></a>CButton::GetCheck  
 Radyo düğmesini veya onay kutusunu onay durumunu alır.  
  
```  
int GetCheck() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme denetimi yönteminden döndürülen değer ile oluşturulmuş **BS_AUTOCHECKBOX**, **bs_autoradıobutton**, **BS_AUTO3STATE**, **BS_CHECKBOX**, **Bs_radıobutton**, veya **BS_3STATE** stili aşağıdaki değerlerden biridir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|**BST_UNCHECKED**|Düğme durumu olarak işaretli değildir.|  
|**BST_CHECKED**|Düğme durumu denetlenir.|  
|**BST_INDETERMINATE**|Düğme durumu belirsiz (yalnızca düğmesi varsa geçerlidir **BS_3STATE** veya **BS_AUTO3STATE** stili).|  
  
 Düğme başka bir stil dönüş değeri ise **BST_UNCHECKED**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="getcursor"></a>CButton::GetCursor  
 İle önceden ayarlanmış bir imleç tanıtıcısı almak için bu üye işlevini çağırın [SetCursor](#setcursor), yani ilişkili bir düğme.  
  
```  
HCURSOR GetCursor();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir imleç görüntüsü için bir tanıtıcı. **NULL** hiçbir imleç önceden belirtilirse.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="geticon"></a>CButton::GetIcon  
 İle önceden ayarlanmış bir simge tanıtıcısı almak için bu üye işlevini çağırın [SetIcon](#seticon), yani ilişkili bir düğme.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simge için bir tanıtıcı. **NULL** hiçbir simge daha önce belirtildiği takdirde.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="getidealsize"></a>CButton::GetIdealSize  
 Düğme denetimi için ideal boyutu alır.  
  
```  
BOOL GetIdealSize(SIZE* psize);
```  
  
### <a name="parameters"></a>Parametreler  
 *psize*  
 Düğmenin geçerli boyutunu gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen **BCM_GETIDEALSIZE** açıklandığı gibi ileti [düğmeleri](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK bölümü.  
  
##  <a name="getimagelist"></a>CButton::GetImageList  
 Resim listesi düğmesi denetiminden almak için bu yöntemi çağırın.  
  
```  
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Parametreler  
 `pbuttonImagelist`  
 Görüntü listesi için bir işaretçi `CButton` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen **BCM_GETIMAGELIST** açıklandığı gibi ileti [düğmeleri](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK bölümü.  
  
##  <a name="getnote"></a>CButton::GetNote  
 Geçerli komut bağlantı denetimi ile ilişkilendirilmiş Not metni alır.  
  
```  
CString GetNote() const;  
  
BOOL GetNote(
    LPTSTR lpszNote,   
    UINT* cchNote) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out]`lpszNote`|İşaretçi bir arabellek ayırma ve serbest bırakma çağıran sorumludur. Dönüş değeri ise `true`arabellek geçerli komut bağlantı denetimi ile ilişkili; Aksi takdirde Not metni içeren, arabellek değiştirilmez.|  
|[içinde out]`cchNote`|Bir işaretçi bir işaretsiz tamsayı değişken.<br /><br /> Bu yöntem çağrıldığında, değişkeni tarafından belirtilen arabellek boyutu içeren `lpszNote` parametresi.<br /><br /> Bu yöntem döndürdüğünde, dönüş değeri ise `true` geçerli komut bağlantı denetimi ile ilişkilendirilmiş Not boyutunu değişken içeriyor. Dönüş değeri ise `false`, Not içermesi gerekir arabellek boyutu değişken içeriyor.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk aşırı içinde bir [CString](../../atl-mfc-shared/using-cstring.md) geçerli komut bağlantı denetimi ile ilişkilendirilmiş Not metni içeren nesne.  
  
 veya  
  
 İkinci aşırı içinde `true` bu yöntem başarılı olursa Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_COMMANDLINK` veya `BS_DEFCOMMANDLINK`.  
  
 Bu yöntem gönderir [BCM_GETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775965) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getnotelength"></a>CButton::GetNoteLength  
 Geçerli komut bağlantı denetimi Not metnin uzunluğunu alır.  
  
```  
UINT GetNoteLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli komut bağlantı denetimi için 16 bit Unicode karakter cinsinden Not metnin uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_COMMANDLINK` veya `BS_DEFCOMMANDLINK`.  
  
 Bu yöntem gönderir [BCM_GETNOTELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb775967) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getsplitglyph"></a>CButton::GetSplitGlyph  
 Geçerli Bölünmüş düğme denetimi ile ilişkilendirilmiş karakteri alır.  
  
```  
TCHAR GetSplitGlyph() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Bölünmüş düğme denetimi ile ilişkilendirilmiş karakter karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir karakterin karakter belirli bir yazı tipi, fiziksel gösterimidir. Örneğin, bir Bölünmüş düğme denetim Unicode onay işareti karakteri karakter ile donatılmış (U + 2713).  
  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_GLYPH` bayrağı ve içinde yapısı gönderir [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) açıklanan iletisi Windows SDK. İleti işlevi döndüğünde, bu yöntem karakter gelen alır `himlGlyph` yapısı üyesi.  
  
##  <a name="getsplitimagelist"></a>CButton::GetSplitImageList  
 Alır [resim listesi](../../mfc/reference/cimagelist-class.md) geçerli Bölünmüş düğme denetimi için.  
  
```  
CImageList* GetSplitImageList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_IMAGE` bayrağı ve içinde yapısı gönderir [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) açıklanan iletisi Windows SDK. İleti işlevi döndüğünde, bu yöntem görüntü listesinden görüntü alır `himlGlyph` yapısı üyesi.  
  
##  <a name="getsplitinfo"></a>CButton::GetSplitInfo  
 Windows geçerli Bölünmüş düğme denetim nasıl çizer belirleyen parametreleri alır.  
  
```  
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out]`pInfo`|İşaretçi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı geçerli Bölünmüş düğme denetimi hakkında bilgi alır. Yapı ayırma için çağıran sorumludur.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bu yöntem gönderir [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getsplitsize"></a>CButton::GetSplitSize  
 Geçerli Bölünmüş düğme denetim açılan bileşeninin sınırlayıcı dikdörtgenini alır.  
  
```  
BOOL GetSplitSize(LPSIZE pSize) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out]`pSize`|İşaretçi bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı dikdörtgen açıklamasını alır.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bölünmüş düğme denetim genişletildiğinde, aşağı açılan bileşen listesi denetimi veya çağrı cihazı denetimi gibi görüntüleyebilirsiniz. Bu yöntem açılan bileşen içeren sınırlayıcı dikdörtgenini alır.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_SIZE` bayrağı ve içinde yapısı gönderir [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) açıklanan iletisi Windows SDK. İleti işlevi döndüğünde, bu yöntem sınırlayıcı dikdörtgenin alır `size` yapısı üyesi.  
  
##  <a name="getsplitstyle"></a>CButton::GetSplitStyle  
 Geçerli bir Bölünmüş düğme denetim tanımlayın Bölünmüş düğme stilleri alır.  
  
```  
UINT GetSplitStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bölünmüş düğme stilleri Bitsel bir birleşimi. Daha fazla bilgi için bkz: `uSplitStyle` üyesi [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bölünmüş düğme stilleri hizalama, en boy oranını ve Bölünmüş düğme simgesine sahip Windows çizer grafik biçiminde belirtin.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_STYLE` bayrağı ve içinde yapısı gönderir [BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) açıklanan iletisi Windows SDK. İleti işlevi döndüğünde, bu yöntem Bölünmüş düğme stillerini alır `uSplitStyle` yapısı üyesi.  
  
##  <a name="getstate"></a>CButton::GetState  
 Düğme denetimi durumunu alır.  
  
```  
UINT GetState() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme denetimi geçerli durumunu belirten değerlerin birleşimi içeren bir bit alanı. Olası değerler aşağıdaki tabloda listelenmektedir.  
  
|Düğme durumu|Değer|Açıklama|  
|------------------|-----------|-----------------|  
|`BST_UNCHECKED`|0x0000|Başlangıç durumu.|  
|`BST_CHECKED`|0X0001|Düğme denetimi denetlenir.|  
|`BST_INDETERMINATE`|0X0002|Durum (üç durumlu düğme denetim sahip olduğunda belirsiz yalnızca) mümkündür.|  
|`BST_PUSHED`|0X0004|Düğme denetimi basıldığında.|  
|`BST_FOCUS`|0X0008|Düğme denetimi odağa sahip.|  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme denetimi ile `BS_3STATE` veya `BS_AUTO3STATE` düğme stili belirlenmemiş bir durum adlı bir üçüncü durumuna sahip bir onay kutusu oluşturur. Durumu belirsiz onay kutusunu işaretli veya işaretsiz olduğunu gösterir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="gettextmargin"></a>CButton::GetTextMargin  
 Metin Kenar almak için bu yöntemi çağırın `CButton` nesnesi.  
  
```  
BOOL GetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Parametreler  
 `pmargin`  
 Metin Kenar gösteren bir işaretçi `CButton` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin Kenar döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen **BCM_GETTEXTMARGIN** açıklandığı gibi ileti [düğmeleri](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK bölümü.  
  
##  <a name="setbitmap"></a>CButton::SetBitmap  
 Yeni bir bitmap düğmesi ile ilişkilendirmek için bu üye işlevini çağırın.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `hBitmap`  
 Bir bit eşlem işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce düğmesi ile ilişkili bir bit eşlem işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem değişmiştir varsayılan olarak ortalanmış düğmesi, otomatik olarak yerleştirilir. Bit eşlem düğmesi için çok büyük ise, her iki tarafında kırpılır. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini seçebilirsiniz:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Aksine [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), düğme başına dört bit eşlemler kullanan `SetBitmap` düğmesi başına yalnızca bir bit eşlem kullanır. Düğmeye basıldığında bit eşlem aşağı ve sağa kaydırma için görünür.  
  
 Bit eşlem ile bittiğinde serbest sorumlu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]  
  
##  <a name="setbuttonstyle"></a>CButton::SetButtonStyle  
 Bir düğme stilini değiştirir.  
  
```  
void SetButtonStyle(
    UINT nStyle,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nStyle`  
 Belirtir [düğmesini stili](../../mfc/reference/styles-used-by-mfc.md#button-styles).  
  
 `bRedraw`  
 Düğme çizilmesi olup olmadığını belirtir. Sıfır olmayan bir değer düğmesini yeniden çizer. 0 değeri düğmesi çizmez. Düğme varsayılan olarak çizilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `GetButtonStyle` düğme stilini almak için üye işlevi. Düşük düzey Tamamla düğmesine stili düğmesi özgü stili sözcüğüdür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]  
  
##  <a name="setcheck"></a>CButton::SetCheck  
 Ayarlar veya radyo düğmesini veya onay kutusunu onay durumunu sıfırlar.  
  
```  
void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>Parametreler  
 `nCheck`  
 Onay durumunu belirtir. Bu parametre, aşağıdakilerden biri olabilir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|**BST_UNCHECKED**|Düğme durumu işaretlenmemiş olarak ayarlayın.|  
|**BST_CHECKED**|Düğme işaretli durumuna ayarlayın.|  
|**BST_INDETERMINATE**|Düğme durumu belirsiz şekilde ayarlayın. Bu değer yalnızca düğmesi varsa kullanılabilir **BS_3STATE** veya **BS_AUTO3STATE** stili.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi bir basma düğmesi üzerinde etkisi yoktur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]  
  
##  <a name="setcursor"></a>CButton::SetCursor  
 Yeni bir imleç düğmesi ile ilişkilendirmek için bu üye işlevini çağırın.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Parametreler  
 `hCursor`  
 Bir imleç işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce düğmesi ile ilişkili bir imleç işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 İmleci, varsayılan olarak ortalanmış düğmesi, değişmiştir otomatik olarak yerleştirilir. İmleç düğmesi için çok büyük ise, her iki tarafında kırpılır. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini seçebilirsiniz:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Farklı [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), düğme başına dört bit eşlemler kullanan `SetCursor` düğmesi başına yalnızca bir imleç kullanır. Düğmeye basıldığında imleci aşağı ve sağa kaydırma için görünür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]  
  
##  <a name="setdropdownstate"></a>CButton::SetDropDownState  
 Geçerli Bölünmüş düğme denetim açılan durumunu ayarlar.  
  
```  
BOOL SetDropDownState(BOOL fDropDown);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`fDropDown`|`true`ayarlamak için `BST_DROPDOWNPUSHED` Aksi takdirde `false`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bölünmüş düğme denetim stili sahip `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON` ve bir düğmeyi ve sağındaki açılan oku oluşur. Daha fazla bilgi için bkz: [düğme stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775951). Genellikle, kullanıcı aşağı açılan okunu tıklattığında açılan durumu ayarlanır. Program aracılığıyla denetimi açılan durumunu ayarlamak için bu yöntemi kullanın. Aşağı açılan okunu durumu göstermek için gölgeli çizilir.  
  
 Bu yöntem gönderir [BCM_SETDROPDOWNSTATE](http://msdn.microsoft.com/library/windows/desktop/bb775973) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_splitButton`, yani Bölünmüş düğme denetim programlı olarak erişmek için kullanılır. Bu değişken, aşağıdaki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde, aşağı açılan okunu gönderilir belirtmek için Bölünmüş düğme denetim durumunu ayarlar.  
  
 [!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]  
  
##  <a name="setelevationrequired"></a>CButton::SetElevationRequired  
 Geçerli düğme denetimi durumunu ayarlar `elevation required`, yükseltilmiş güvenlik simge görüntülemek denetim için gerekli olduğu.  
  
```  
BOOL SetElevationRequired(BOOL fElevationRequired);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`fElevationRequired`|`true`ayarlamak için `elevation required` Aksi takdirde `false`.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme veya komut bağlantı denetimi bir eylemi gerçekleştirmek için yükseltilmiş güvenlik izni gerektiriyorsa, Denetim kümesine `elevation required` durumu. Sonuç olarak, Windows kullanıcı hesabı denetimi (UAC) Kalkan simgesi denetiminde görüntüler. Daha fazla bilgi için bkz: "Kullanıcı hesabı denetimi" [MSDN](http://go.microsoft.com/fwlink/linkid=18507).  
  
 Bu yöntem gönderir [BCM_SETSHIELD](http://msdn.microsoft.com/library/windows/desktop/bb775979) Windows SDK'ın açıklanan ileti.  
  
##  <a name="seticon"></a>CButton::SetIcon  
 Düğme ile yeni bir simge ilişkilendirmek için bu üye işlevini çağırın.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 `hIcon`  
 Simge işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce düğmesi ile ilişkili bir simge işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 Simge, varsayılan olarak ortalanmış düğmesi, değişmiştir otomatik olarak yerleştirilir. Simge düğmesi için çok büyük ise, her iki tarafında kırpılır. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini seçebilirsiniz:  
  
- **BS_TOP**  
  
- **BS_LEFT**  
  
- **BS_RIGHT**  
  
- **BS_CENTER**  
  
- **BS_BOTTOM**  
  
- **BS_VCENTER**  
  
 Aksine [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), düğme başına dört bit eşlemler kullanan `SetIcon` düğmesi başına yalnızca bir simge kullanır. Düğmeye basıldığında aşağı ve sağa kaydırma için simgesi görünür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]  
  
##  <a name="setimagelist"></a>CButton::SetImageList  
 Görüntü listesi ayarlamak için bu yöntemi çağırın `CButton` nesnesi.  
  
```  
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```  
  
### <a name="parameters"></a>Parametreler  
 `pbuttonImagelist`  
 Yeni resim listesi için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **TRUE** başarılı, **FALSE** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen **BCM_SETIMAGELIST** açıklandığı gibi ileti [düğmeleri](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK bölümü.  
  
##  <a name="setnote"></a>CButton::SetNote  
 Not metni geçerli komut bağlantı denetimi için ayarlar.  
  
```  
BOOL SetNote(LPCTSTR lpszNote);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`lpszNote`|Komut bağlantı denetimi için Not metin olarak ayarlanmış bir UNICODE dizesi işaretçi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_COMMANDLINK` veya `BS_DEFCOMMANDLINK`.  
  
 Bu yöntem gönderir [BCM_SETNOTE](http://msdn.microsoft.com/library/windows/desktop/bb775977) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_cmdLink`, yani komutu bağlantı denetimi programlı olarak erişmek için kullanılır. Bu değişken, aşağıdaki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde Not metin komutu bağlantı denetimi için ayarlar.  
  
 [!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]  
  
##  <a name="setsplitglyph"></a>CButton::SetSplitGlyph  
 Belirtilen bir karakterin geçerli Bölünmüş düğme denetimi ile ilişkilendirir.  
  
```  
BOOL SetSplitGlyph(TCHAR chGlyph);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`chGlyph`|Bölünmüş düğme aşağı açılan okunu kullanılacak karakter belirtir karakter.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme stilini sahip denetimleriyle bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bir karakterin karakter belirli bir yazı tipi, fiziksel gösterimidir. `chGlyph` Parametresi karakter kullanılmaz, ancak bunun yerine sistem tarafından tanımlanan karakterlerin kümesinden bir karakter seçmek için kullanılır. Varsayılan aşağı açılan okunu karakter karakteriyle '6' belirtilir ve Unicode karakter aşağı siyah ÜÇGEN (U + 25BC) benzer.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_GLYPH` bayrağı ve `himlGlyph` üyesiyle `chGlyph` parametre ve yapısıgönderir[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK'ın açıklanan ileti.  
  
##  <a name="setsplitimagelist"></a>CButton::SetSplitImageList  
 İlişkilendiren bir [resim listesi](../../mfc/reference/cimagelist-class.md) geçerli Bölünmüş düğme denetimi ile.  
  
```  
BOOL SetSplitImageList(CImageList* pSplitImageList);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pSplitImageList`|İşaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) geçerli Bölünmüş düğme denetim atamak için nesne.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_IMAGE` bayrağı ve `himlGlyph` üyesiyle `pSplitImageList` parametre ve yapısıgönderir[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK'ın açıklanan ileti.  
  
##  <a name="setsplitinfo"></a>CButton::SetSplitInfo  
 Windows geçerli Bölünmüş düğme denetim nasıl çizer belirleyen parametreleri belirtir.  
  
```  
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pInfo`|İşaretçi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) geçerli Bölünmüş düğme denetim tanımlar yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bu yöntem gönderir [BCM_SETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775981) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_splitButton`, yani Bölünmüş düğme denetim programlı olarak erişmek için kullanılır.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde Bölünmüş düğme aşağı açılan okunu için kullanılan karakter değiştirir. Örneğin, bir varsayılan aşağı işaret eden üçgen karakter yukarı dönük üçgen karakter değiştirir. Belirttiğiniz karakter görüntülenen karakter bağlıdır `himlGlyph` üyesi `BUTTON_SPLITINFO` yapısı. Aşağı işaret eden üçgen karakter karakteriyle ' 6 belirtildi 've yukarı dönük üçgen karakter karakteriyle ' 5 belirtildiğinden'. Kolaylık yöntemi karşılaştırması için bkz: [CButton::SetSplitGlyph](#setsplitglyph).  
  
 [!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]  
  
##  <a name="setsplitsize"></a>CButton::SetSplitSize  
 Geçerli Bölünmüş düğme denetim açılan bileşeninin sınırlayıcı dikdörtgenini ayarlar.  
  
```  
BOOL SetSplitSize(LPSIZE pSize);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`pSize`|İşaretçi bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) sınırlayıcı dikdörtgenini açıklar yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bölünmüş düğme denetim genişletildiğinde, aşağı açılan bileşen listesi denetimi veya çağrı cihazı denetimi gibi görüntüleyebilirsiniz. Bu yöntem açılan bileşen içeren sınırlayıcı dikdörtgenini boyutunu belirtir.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_SIZE` bayrağı ve `size` üyesiyle `pSize` parametre ve yapısıgönderir[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_splitButton`, yani Bölünmüş düğme denetim programlı olarak erişmek için kullanılır. Bu değişken, aşağıdaki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde Bölünmüş düğme aşağı açılan oku boyutunu iki katına çıkar.  
  
 [!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]  
  
##  <a name="setsplitstyle"></a>CButton::SetSplitStyle  
 Geçerli Bölünmüş düğme denetim stilini ayarlar.  
  
```  
BOOL SetSplitStyle(UINT uSplitStyle);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in]`uSplitStyle`|Bölünmüş düğme stilleri Bitsel bir birleşimi. Daha fazla bilgi için bkz: `uSplitStyle` üyesi [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca, düğme stili denetimleri ile bu yöntemi kullanmak `BS_SPLITBUTTON` veya `BS_DEFSPLITBUTTON`.  
  
 Bölünmüş düğme stilleri hizalama, en boy oranını ve Bölünmüş düğme simgesine sahip Windows çizer grafik biçiminde belirtin. Daha fazla bilgi için bkz: `uSplitStyle` üyesi [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı.  
  
 Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775955) yapısı `BCSIF_STYLE` bayrağı ve `uSplitStyle` üyesiyle `uSplitStyle` parametre ve yapısıgönderir[ BCM_GETSPLITINFO](http://msdn.microsoft.com/library/windows/desktop/bb775969) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde değişkeni tanımlar `m_splitButton`, yani Bölünmüş düğme denetim programlı olarak erişmek için kullanılır.  
  
 [!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde Bölünmüş düğme açılan ok stilini ayarlar. `BCSS_ALIGNLEFT` Stili düğmesi sol tarafta oku görüntüler ve `BCSS_STRETCH` Stili düğmesini yeniden boyutlandırdığınızda aşağı açılan okunu 's oranlarını korur.  
  
 [!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]  
  
##  <a name="setstate"></a>CButton::SetState  
 Düğme denetimi veya vurgulanan olup olmadığını belirler.  
  
```  
void SetState(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parametreler  
 *bHighlight*  
 Düğme vurgulanmasını olup olmadığını belirtir. Sıfır olmayan bir değer düğmesi vurgular; 0 değeri hiçbir vurgulama kaldırır.  
  
### <a name="remarks"></a>Açıklamalar  
 Vurgulama düğme denetimi dış etkiler. Radyo düğmesini veya onay kutusuna onay durumu üzerinde bir etkisi yoktur.  
  
 Düğme denetimi, kullanıcı tıkladığında ve sol fare düğmesini tutan otomatik olarak vurgulanır. Kullanıcının fare düğmesini bıraktığında Vurgulama kaldırılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]  
  
##  <a name="settextmargin"></a>CButton::SetTextMargin  
 Metin Kenar ayarlamak için bu yöntemi çağırın `CButton` nesnesi.  
  
```  
BOOL SetTextMargin(RECT* pmargin);
```  
  
### <a name="parameters"></a>Parametreler  
 `pmargin`  
 Yeni metin kenar gösteren bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa TRUE döndürür başarısız olduğunda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen **BCM_SETTEXTMARGIN** açıklandığı gibi ileti [düğmeleri](http://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK bölümü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [CScrollBar sınıfı](../../mfc/reference/cscrollbar-class.md)   
 [CStatic sınıfı](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton sınıfı](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog sınıfı](../../mfc/reference/cdialog-class.md)
