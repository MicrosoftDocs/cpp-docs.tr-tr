---
title: CComboBoxEx sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
dev_langs:
- C++
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c3626fbdba9fcf34364237e8970e5b941ecce9d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201532"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx sınıfı
Birleşik giriş kutusu denetim görüntü listeleri için destek sağlayarak genişletir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Oluşturur bir `CComboBoxEx` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|Birleşik giriş kutusu oluşturur ve ona ekler `CComboBoxEx` nesne.|  
|[CComboBoxEx::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleriyle bir birleşik giriş kutusu oluşturur ve ona ekler bir `ComboBoxEx` nesne.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Bir öğe kaldırır bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Alt birleşik giriş kutusu denetimi için bir işaretçi alır.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Düzenle denetim kısmı tanıtıcısını alır bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|İçin kullanılan genişletilmiş stiller alır bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::GetImageList](#getimagelist)|Atanan görüntü listesine bir işaretçi alır bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::GetItem](#getitem)|Öğesi için bilgi alır bir verilen `ComboBoxEx` öğesi.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Kullanıcı içeriğini değişip değişmediğini belirleyen `ComboBoxEx` yazarak düzenleme denetimi.|  
|[CComboBoxEx::InsertItem](#insertitem)|İçinde yeni bir öğe ekler bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|Genişletilmiş stiller içinde ayarlar bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::SetImageList](#setimagelist)|Görüntü listesi için ayarlar bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::SetItem](#setitem)|Öznitelikleri bir öğe için ayarlar bir `ComboBoxEx` denetimi.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Görsel stili, Genişletilmiş Birleşik giriş kutusu denetimi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak `CComboBoxEx` birleşik giriş kutusu denetimleri oluşturma için artık kod çizim kendi görüntünüzü uygulamak gerekir. Bunun yerine, `CComboBoxEx` bir görüntü listesinden görüntü erişim için.  
  
## <a name="image-list-support"></a>Görüntü listesi desteği  
 Standart açılan kutuda, sahip çizim denetimi olarak birleşik giriş kutusu oluşturarak görüntü çizmek için birleşik giriş kutusu sahibi sorumludur. Kullanırken `CComboBoxEx`, çünkü bunlar kapsanan cbs_ownerdrawfıxed ve cbs_hasstrıngs çizim stilleri ayarlama gerekmez. Aksi takdirde, çizim işlemlerini gerçekleştirmek için kod yazmanız gerekir. A `CComboBoxEx` denetim öğesi başına en fazla üç görüntüleri destekler: seçili durumda, seçili olmayan bir durum için diğeri için katmana görüntü için bir tane.  
  
## <a name="styles"></a>Stilleri  
 `CComboBoxEx` cbs_sımple, CBS_DROPDOWN cbs_dropdownlıst ve WS_CHILD stillerini destekler. Pencere oluşturulurken geçirilen diğer tüm stiller, denetim tarafından göz ardı edilir. Pencerenin oluşturulduktan sonra diğer birleşik giriş kutusu stilleri çağırarak sağlayabilirsiniz `CComboBoxEx` üye işlevi [SetExtendedStyle](#setextendedstyle). Bu stiller ile şunları yapabilirsiniz:  
  
-   Büyük küçük harfe duyarlı olması için listedeki kümesi dize arar.  
  
-   Oluşturma ('/'), eğik kullanan bir birleşik giriş kutusu denetimi ters eğik çizgi ('\\') ve nokta ('. ') karakter Sözcük ayırıcılar olarak. Bu kullanıcıların gelen word Word'ün, CTRL + ok klavye kısayolunu kullanarak atlama olanak tanır.  
  
-   Birleşik giriş kutusu denetimi görüntülemek veya görüntülememek görüntü ayarlayın. Hiçbir görüntü gösterilirse, birleşik giriş kutusu görüntü gönderme metin girinti kaldırabilirsiniz.  
  
-   İçerdiği geniş birleşik giriş kutusu küçük şekilde boyutlandırdıktan dahil olmak üzere bir dar birleşik giriş kutusu denetimi oluşturun.  
  
 Bu stil daha ayrıntılı açıklanır bayraklar [CComboBoxEx kullanma](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Bekletme ve geri çağırma öğesi öznitelikleri öğesi  
 Gibi öğeleri ve görüntü, girinti değerleri ve metin dizelerini için dizinleri öğesi bilgilerini Win32 yapısında depolanmış [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema)Windows SDK içinde açıklandığı gibi. Yapısı, geri çağırma bayrakları için karşılık gelen üyeleri de içerir.  
  
 Ayrıntılı, kavramsal tartışma için bkz [CComboBoxEx kullanma](../../mfc/using-ccomboboxex.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx  
 Bu üye işlevi çağrısı bir `CComboBoxEx` nesne.  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>  CComboBoxEx::Create  
 Birleşik giriş kutusu oluşturur ve ona ekler `CComboBoxEx` nesne.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwStyle*  
 Açılan kutu uygulanan birleşik giriş kutusu stilleri bileşimini belirtir. Bkz: **açıklamalar** aşağıda stilleri hakkında daha fazla bilgi.  
  
 *Rect*  
 Bir başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne veya [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) birleşik giriş kutusunun boyutunu ve konumunu olan yapısı.  
  
 *pParentWnd*  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) birleşik giriş kutusunun üst pencere nesnesini (genellikle bir `CDialog`). NULL olmamalıdır.  
  
 *nID*  
 Açılan kutunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla oluşturuldu olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma bir `CComboBoxEx` iki adımda nesnesi:  
  
1.  Çağrı [CComboBoxEx](#ccomboboxex) oluşturmak için bir `CComboBoxEx` nesne.  
  
2.  Genişletilmiş Windows birleşik giriş kutusu oluşturur ve ona ekler, bu üye işlevi çağrısı `CComboBoxEx` nesne.  
  
 Çağırdığınızda `Create`, MFC ortak denetimler başlatır.  
  
 Birleşik giriş kutusu oluşturduğunuzda, aşağıdaki birleşik giriş kutusu stilleri bir bölümünü veya tamamını belirtebilirsiniz:  
  
- CBS_SIMPLE  
  
- CBS_DROPDOWN  
  
- CBS_DROPDOWNLIST  
  
- CBS_AUTOHSCROLL  
  
- WS_CHILD  
  
 Pencere oluşturulurken geçirilen diğer tüm stiller göz ardı edilir. `ComboBoxEx` Denetimi, ek özellikler sağlamak genişletilmiş stiller de destekler. Bu stiller açıklanan [ComboBoxEx denetim genişletilmiş stiller](/windows/desktop/Controls/comboboxex-control-extended-styles), Windows SDK. Çağırarak bu stilleri ayarlama [SetExtendedStyle](#setextendedstyle).  
  
 Genişletilmiş windows stilleri ile denetiminizi kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine `Create`.  
  
##  <a name="createex"></a>  CComboBoxEx::CreateEx  
 Genişletilmiş Birleşik giriş kutusu denetimi (alt pencere) oluşturun ve ilişkilendirmek için bu işlevi çağırın `CComboBoxEx` nesne.  
  
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
 Oluşturulan denetimin genişletilmiş stilini belirtir. Genişletilmiş Windows stilleri bir listesi için bkz. *dwExStyle* parametresi için [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK.  
  
 *dwStyle*  
 Birleşik giriş kutusu denetiminin stili. Bkz: [Oluştur](#create) stilleri listesi.  
  
 *Rect*  
 Bir başvuru bir [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) istemci koordinatları olarak oluşturulması için pencerenin konumunu ve boyutunu açıklayan yapısı *pParentWnd*.  
  
 *pParentWnd*  
 Denetimin ana penceresine bir işaretçi.  
  
 *nID*  
 Denetimin alt penceresi kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine `Create` Windows genişletilmiş sitil önsöz tarafından belirtilen Genişletilmiş Windows stilleri uygulamak için **WS_EX_**.  
  
 `CreateEx` tarafından belirtilen Genişletilmiş Windows stillerle denetimi oluşturur *dwExStyle*. Genişletilmiş stiller belirli bir Genişletilmiş Birleşik giriş kutusunu kullanarak denetim ayarlamalısınız [SetExtendedStyle](#setextendedstyle). Örneğin, `CreateEx` böyle stilleri WS_EX_CONTEXTHELP ayarlandı, ancak kullanmak için `SetExtendedStyle` böyle stilleri CBES_EX_CASESENSITIVE ayarlanacak. Daha fazla bilgi için bkz. Bu konu başlığı altında açıklanan stilleri [ComboBoxEx denetimin Genişletilmiş Stil](/windows/desktop/Controls/comboboxex-control-extended-styles) Windows SDK.  
  
##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem  
 Bir öğe kaldırır bir `ComboBoxEx` denetimi.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *İIndex*  
 Kaldırılacak öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kalan denetiminde öğe sayısı. Varsa *İIndex* olan geçersiz işlev CB_ERR döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygular [CBEM_DELETEITEM](/windows/desktop/Controls/cbem-deleteitem)Windows SDK içinde açıklandığı gibi. DeleteItem, çağırdığınızda bir [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) CBEN_DELETEITEM bildirim iletisi üst pencereye gönderilir.  
  
##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl  
 Birleşik giriş kutusu denetimi içinde bir işaretçi almak için bu üye işlevi çağrısı bir `CComboBoxEx` nesne.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CComboBox` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `CComboBoxEx` Denetimini kapsülleyen bir üst penceresine oluşan bir `CComboBox`.  
  
 `CComboBox` Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve sonraki boşta işleme sırada yok edilir.  
  
##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl  
 Bir işaretçi için birleşik giriş kutusu düzenleme denetimine almak için bu üye işlevini çağırın.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CEdit](../../mfc/reference/cedit-class.md) nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CComboBoxEx` CBS_DROPDOWN stiliyle oluşturulduğunda bir düzenleme kutusu denetimi kullanır.  
  
 `CEdit` Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve sonraki boşta işleme sırada yok edilir.  
  
##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle  
 Çağırmak için kullanılan genişletilmiş stiller almak için bu üye işlevi bir `CComboBoxEx` denetimi.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birleşik giriş kutusu denetimi için kullanılan genişletilmiş stiller içeren DWORD değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ComboBoxEx denetimin Genişletilmiş Stil](/windows/desktop/Controls/comboboxex-control-extended-styles) bu stilleri hakkında daha fazla bilgi için Windows SDK.  
  
##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList  
 Bir işaretçi tarafından kullanılan görüntü listesini almak için bu üye işlevi çağrısı bir `CComboBoxEx` denetimi.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne. Başarısız olursa, bu üye işlev NULL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `CImageList` Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve sonraki boşta işleme sırada yok edilir.  
  
##  <a name="getitem"></a>  CComboBoxEx::GetItem  
 Öğesi için bilgi alır bir verilen `ComboBoxEx` öğesi.  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pCBItem*  
 Bir işaretçi bir [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) öğesi bilgilerini alacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygular [CBEM_GETITEM](/windows/desktop/Controls/cbem-getitem)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged  
 Kullanıcı içeriğini değişip değişmediğini belirleyen `ComboBoxEx` yazarak düzenleme denetimi.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcının denetimin düzenleme kutusuna yazdığını olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygular [CBEM_HASEDITCHANGED](/windows/desktop/Controls/cbem-haseditchanged)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="insertitem"></a>  CComboBoxEx::InsertItem  
 İçinde yeni bir öğe ekler bir `ComboBoxEx` denetimi.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pCBItem*  
 Bir işaretçi bir [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) öğesi bilgilerini alacak yapısı. Bu yapı öğesi için geri çağırma bayrağı değerler içeriyor.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizin; başarılı olursa, yeni öğe eklendi Aksi takdirde-1.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdığınızda `InsertItem`, [wm_notıfy](https://msdn.microsoft.com/library/windows/desktop/bb775583) ile ileti [CBEN_INSERTITEM](/windows/desktop/Controls/cben-insertitem) bildirim üst pencereye gönderilir.  
  
##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle  
 Denetimin Genişletilmiş Birleşik giriş kutusu için kullanıldı genişletilmiş stiller ayarlamak için bu üye işlevini çağırın.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwExMask*  
 Hangi stillerde gösteren bir DWORD değeri *dwExStyles* etkilenecek olan. Yalnızca genişletilmiş stilleri *dwExMask* değiştirilecek. Diğer tüm stiller olarak korunur. Bu parametre sıfır, ardından tüm stilleri ise *dwExStyles* etkilenecek.  
  
 *dwExStyles*  
 Genişletilmiş denetim için ayarlanacak stiller birleşik giriş kutusu denetimi içeren bir DWORD değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim için daha önce kullanılan genişletilmiş stiller içeren bir DWORD değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ComboBoxEx denetimin Genişletilmiş Stil](/windows/desktop/Controls/comboboxex-control-extended-styles) bu stilleri hakkında daha fazla bilgi için Windows SDK.  
  
 Denetimin genişletilmiş windows stillerle Genişletilmiş Birleşik giriş kutusu oluşturmak için kullanın [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList  
 Görüntü listesi için ayarlar bir `ComboBoxEx` denetimi.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 *pImageList*  
 Bir işaretçi bir `CImageList` ile kullanmak üzere istediğiniz görüntüyü içeren nesne `CComboBoxEx` denetimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) tarafından daha önce kullanılan görüntülerin içeren nesne `CComboBoxEx` denetimi. Hiçbir görüntü listesi önceden ayarlanan yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygular [CBEM_SETIMAGELIST](/windows/desktop/Controls/cbem-setimagelist)Windows SDK içinde açıklandığı gibi. Varsayılan düzenleme denetiminin yüksekliğini değiştirirseniz, Win32 işlevini çağırmak [SetWindowPos](https://msdn.microsoft.com/library/windows/desktop/ms633545) çağırdıktan sonra denetiminizi yeniden boyutlandırmak için `SetImageList`, ya da düzgün görüntülenmez.  
  
 `CImageList` Dönüş değeri tarafından işaret edilen nesne geçici bir nesne ve sonraki boşta işleme sırada yok edilir.  
  
##  <a name="setitem"></a>  CComboBoxEx::SetItem  
 Öznitelikleri bir öğe için ayarlar bir `ComboBoxEx` denetimi.  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parametreler  
 *pCBItem*  
 Bir işaretçi bir [COMBOBOXEXITEM](/windows/desktop/api/commctrl/ns-commctrl-tagcomboboxexitema) öğesi bilgilerini alacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygular [CBEM_SETITEM](/windows/desktop/Controls/cbem-setitem)Windows SDK içinde açıklandığı gibi.  
  
##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme  
 Görsel stili, Genişletilmiş Birleşik giriş kutusu denetimi ayarlar.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pszSubAppName*  
 Ayarlanacak Genişletilmiş Birleşik giriş kutusu görsel stil içeren bir Unicode dize işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğine öykünür [CBEM_SETWINDOWTHEME](/windows/desktop/Controls/cbem-setwindowtheme) Windows SDK içinde açıklandığı gibi ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCIE](../../visual-cpp-samples.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)
