---
title: CComboBoxEx sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
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
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3aecbb168316b3d6416d3a41a6f6a56b04aeb990
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomboboxex-class"></a>CComboBoxEx sınıfı
Birleşik giriş kutusu denetimi resim listeleri için destek sağlayarak genişletir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|Oluşturan bir `CComboBoxEx` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|Birleşik giriş kutusu oluşturur ve ona ekler `CComboBoxEx` nesnesi.|  
|[CComboBoxEx::CreateEx](#createex)|Belirtilen Windows genişletilmiş stilleri birleşik giriş kutusu oluşturur ve ekler bir **ComboBoxEx** nesnesi.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|Bir öğeden kaldırır bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|Alt birleşik giriş kutusu denetimi için bir işaretçi alır.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|Düzenle denetim kısmı tanıtıcısını alır bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|İçin kullanılmakta olan Genişletilmiş stili alır bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::GetImageList](#getimagelist)|Atanan resim listesi için bir işaretçi alır bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::GetItem](#getitem)|Alır öğesi için bilgi bir verilen **ComboBoxEx** öğesi.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|Kullanıcı içeriğini değişip değişmediğini belirleyen **ComboBoxEx** yazarak denetim düzenleyin.|  
|[CComboBoxEx::InsertItem](#insertitem)|Yeni bir öğe ekler bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|İçinde genişletilmiş stillerini ayarlar bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::SetImageList](#setimagelist)|Görüntü listesi için ayarlar bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::SetItem](#setitem)|Bir öğeyi özniteliklerini ayarlar bir **ComboBoxEx** denetim.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Görsel stilini Genişletilmiş Birleşik giriş kutusu denetimi ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak `CComboBoxEx` birleşik giriş kutusu denetimleri oluşturmak için artık kod çizim kendi görüntünüzü yapması gerekir. Bunun yerine, kullanın `CComboBoxEx` resim listesi erişim görüntülerden için.  
  
## <a name="image-list-support"></a>Resim listesi desteği  
 Bir standart birleşik giriş kutusu sahip çizim denetimi olarak birleşik giriş kutusu oluşturarak resim çizim için birleşik giriş kutusu sahibi sorumludur. Kullandığınızda `CComboBoxEx`, çizim stilleri ayarlama gerekmez **cbs_ownerdrawfıxed** ve **cbs_hasstrıngs** kapsanan çünkü. Aksi takdirde, çizim işlemleri gerçekleştirmek için kod yazmanız gerekir. A `CComboBoxEx` denetimi öğesi başına en fazla üç görüntüleri destekler: seçilen bir durumu, seçili durumu için diğeri için katmana görüntü için bir tane.  
  
## <a name="styles"></a>Stilleri  
 `CComboBoxEx`stillerini destekler **cbs_sımple**, **CBS_DROPDOWN**, **cbs_dropdownlıst**, ve **WS_CHILD**. Pencerenin oluşturduğunuzda, geçirilen tüm stilleri denetim tarafından göz ardı edilir. Pencerenin oluşturulduktan sonra diğer birleşik giriş kutusu stilleri çağırarak sağlayabilirsiniz `CComboBoxEx` üye işlevi [SetExtendedStyle](#setextendedstyle). Bu stiller ile şunları yapabilirsiniz:  
  
-   Büyük küçük harfe duyarlı olması için listedeki kümesi dize arar.  
  
-   Oluşturma ('/'), eğik çizgi kullanan bir birleşik giriş kutusu denetimi ters eğik çizgi ('\\') ve süresi ('. ') karakter word ayırıcısı olarak. Bu gelen word Word'ün, CTRL + ok klavye kısayolunu kullanarak atlamak kullanıcılara izin verin.  
  
-   Birleşik giriş kutusu denetimi görüntülemek veya bir görüntü görüntülememek için ayarlayın. Birleşik giriş kutusu hiçbir resim görüntüleniyorsa, görüntüyü düzenler metin girinti kaldırabilirsiniz.  
  
-   İçerdiği genişleterek açılan kutu kırpar şekilde boyutlandırma dahil olmak üzere bir dar birleşik giriş kutusu denetimi oluşturun.  
  
 Bu stili bayrakları daha ayrıntılı açıklanır [kullanarak CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="item-retention-and-callback-item-attributes"></a>Bekletme ve geri arama öğesi öznitelikleri öğesi  
 Gibi öğeleri ve görüntüleri, girinti değerleri ve metin dizelerini için dizin öğesi bilgileri Win32 yapısında depolanmış [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746), Windows SDK'ın açıklandığı gibi. Yapı geri çağırma bayrakları karşılık üyeleri de içerir.  
  
 Ayrıntılı, kavramsal tartışma için bkz: [kullanarak CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx  
 Oluşturmak için bu üye işlevini çağırın bir `CComboBoxEx` nesnesi.  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>CComboBoxEx::Create  
 Birleşik giriş kutusu oluşturur ve ona ekler `CComboBoxEx` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Birleşik giriş kutusu stilleri açılan kutu uygulanan bileşimini belirtir. Bkz: **açıklamalar** aşağıda stilleri hakkında daha fazla bilgi için.  
  
 `rect`  
 Bir başvuru bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesne veya [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) konum ve boyutlarının birleşik giriş kutusu yapısı.  
  
 `pParentWnd`  
 Bir işaretçi bir [CWnd](../../mfc/reference/cwnd-class.md) açılan kutunun üst pencere nesnesi (genellikle bir `CDialog`). Değil olmalıdır **NULL**.  
  
 `nID`  
 Açılan kutunun denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne başarıyla oluşturuldu, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma bir `CComboBoxEx` iki adımda nesnesi:  
  
1.  Çağrı [CComboBoxEx](#ccomboboxex) oluşturmak için bir `CComboBoxEx` nesnesi.  
  
2.  Genişletilmiş Windows birleşik giriş kutusu oluşturur ve ekler bu üye işlevini çağırın `CComboBoxEx` nesnesi.  
  
 Çağırdığınızda **oluşturma**, MFC ortak denetimler başlatır.  
  
 Birleşik giriş kutusu oluşturduğunuzda, aşağıdaki birleşik giriş kutusu stilleri bir bölümünü veya tamamını belirtebilirsiniz:  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 Pencerenin oluşturduğunuzda, geçirilen tüm stilleri göz ardı edilir. **ComboBoxEx** denetimi de ek özellikler sağlamak genişletilmiş stillerini destekler. Bu stiller açıklanan [ComboBoxEx kontrol genişletilmiş stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775742), Windows SDK'sındaki. Bu stiller aranarak [SetExtendedStyle](#setextendedstyle).  
  
 Genişletilmiş windows stilleri denetimi ile kullanmak istiyorsanız, çağrı [CreateEx](#createex) yerine **oluşturma**.  
  
##  <a name="createex"></a>CComboBoxEx::CreateEx  
 Genişletilmiş Birleşik giriş kutusu denetimi (alt pencere) oluşturun ve bunu ile ilişkilendirmek için bu işlevi çağırmak `CComboBoxEx` nesnesi.  
  
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
 Birleşik giriş kutusu denetiminin stili. Bkz: [oluşturma](#create) stilleri listesi.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı `pParentWnd`.  
  
 `pParentWnd`  
 Denetimin üst penceresi için bir işaretçi.  
  
 `nID`  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine **oluşturma** Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
 `CreateEx`Denetim tarafından belirtilen Genişletilmiş Windows stillerini oluşturur `dwExStyle`. Genişletilmiş stilleri belirli bir Genişletilmiş Birleşik giriş kutusunu kullanarak denetim ayarlamalısınız [SetExtendedStyle](#setextendedstyle). Örneğin, `CreateEx` böyle stilleri olarak ayarlamak için **WS_EX_CONTEXTHELP**, ancak `SetExtendedStyle` böyle stilleri olarak ayarlamak için **CBES_EX_CASESENSITIVE**. Daha fazla bilgi için bkz. konu başlığı altında açıklanan stilleri [ComboBoxEx denetim genişletilmiş stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775742) Windows SDK.  
  
##  <a name="deleteitem"></a>CComboBoxEx::DeleteItem  
 Bir öğeden kaldırır bir **ComboBoxEx** denetim.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `iIndex`  
 Kaldırılacak öğenin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetim içinde kalan öğe sayısı. Varsa `iIndex` işlevi döndürür, geçersiz **CB_ERR**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygulayan [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768), Windows SDK'ın açıklandığı gibi. DeleteItem, çağırdığınızda bir [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) ile ileti **CBEN_DELETEITEM** üst penceresine bildirim gönderilir.  
  
##  <a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl  
 Birleşik giriş kutusu denetimi içinde bir işaretçi almak için bu üye işlevini çağırın bir `CComboBoxEx` nesnesi.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir `CComboBox` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CComboBoxEx` Denetimi oluşur yalıtan bir üst pencere bir `CComboBox`.  
  
 `CComboBox` Dönüş değeri tarafından işaret nesnesi geçici bir nesne ve sonraki boşta kalma işleme süresinde yok.  
  
##  <a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl  
 Bir işaretçi bir birleşik giriş kutusu düzenleme denetimi almak için bu üye işlevini çağırın.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [CEdit](../../mfc/reference/cedit-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 A `CComboBoxEx` denetimi kullanan bir düzenleme kutusu ile oluşturulduğunda **CBS_DROPDOWN** stili.  
  
 `CEdit` Dönüş değeri tarafından işaret nesnesi geçici bir nesne ve sonraki boşta kalma işleme süresinde yok.  
  
##  <a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle  
 İçin kullanılan genişletilmiş stilleri almak için bu üye işlevini çağırın bir `CComboBoxEx` denetim.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `DWORD` Birleşik giriş kutusu denetimi için kullanılan genişletilmiş stilleri içeren değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ComboBoxEx denetim genişletilmiş stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775742) bu stiller hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
##  <a name="getimagelist"></a>CComboBoxEx::GetImageList  
 Tarafından kullanılan resim listesi için bir işaretçi almak için bu üye işlevini çağırın bir `CComboBoxEx` denetim.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesnesi. Bu başarısız olursa, bu üye işlevinin döndürdüğü **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 `CImageList` Dönüş değeri tarafından işaret nesnesi geçici bir nesne ve sonraki boşta kalma işleme süresinde yok.  
  
##  <a name="getitem"></a>CComboBoxEx::GetItem  
 Alır öğesi için bilgi bir verilen **ComboBoxEx** öğesi.  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCBItem`  
 Bir işaretçi bir [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) madde bilgilerini alacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygulayan [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="haseditchanged"></a>CComboBoxEx::HasEditChanged  
 Kullanıcı içeriğini değişip değişmediğini belirleyen **ComboBoxEx** yazarak denetim düzenleyin.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı denetiminin düzenleme kutusuna yazdıysanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygulayan [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="insertitem"></a>CComboBoxEx::InsertItem  
 Yeni bir öğe ekler bir **ComboBoxEx** denetim.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCBItem`  
 Bir işaretçi bir [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) madde bilgilerini alacak yapısı. Bu yapı öğesi için geri çağırma bayrak değeri içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, yeni öğe eklendi dizin; Aksi takdirde-1.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdığınızda `InsertItem`, [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) ile ileti [CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764) üst penceresine bildirim gönderilir.  
  
##  <a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle  
 Denetim Genişletilmiş Birleşik giriş kutusu için kullanılan genişletilmiş stilleri ayarlamak için bu üye işlevini çağırın.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExMask`  
 A `DWORD` hangi stillerde gösteren değer `dwExStyles` etkilenecek üzeresiniz. Yalnızca genişletilmiş stillerde `dwExMask` değiştirilecek. Diğer tüm stilleri olarak korunur. Bu parametre sıfır sonra tüm stillerde ise `dwExStyles` etkilenecek.  
  
 `dwExStyles`  
 A `DWORD` birleşik giriş kutusu içeren değerini denetlemek için Denetim ayarlamak için genişletilmiş stili.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `DWORD` denetim için daha önce kullanılan genişletilmiş stilleri içeren değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [ComboBoxEx denetim genişletilmiş stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775742) bu stiller hakkında daha fazla bilgi için Windows SDK'sındaki.  
  
 Genişletilmiş windows stilleri denetimiyle Genişletilmiş Birleşik giriş kutusu oluşturmak için kullanın [CreateEx](#createex).  
  
##  <a name="setimagelist"></a>CComboBoxEx::SetImageList  
 Görüntü listesi için ayarlar bir **ComboBoxEx** denetim.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parametreler  
 `pImageList`  
 Bir işaretçi bir `CImageList` ile kullanılacak görüntüleri içeren bir nesne `CComboBoxEx` denetim.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) tarafından daha önce kullanılan görüntüleri içeren bir nesne `CComboBoxEx` denetim. **NULL** hiçbir resim listesi daha önce ayarlandıysa.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygulayan [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787), Windows SDK'ın açıklandığı gibi. Varsayılan düzenleme denetimi yüksekliğini değiştirirseniz, Win32 işlevi çağrısı [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) çağırdıktan sonra denetiminizi yeniden boyutlandırmak için `SetImageList`, ya da düzgün görüntülenmez.  
  
 `CImageList` Dönüş değeri tarafından işaret nesnesi geçici bir nesne ve sonraki boşta kalma işleme süresinde yok.  
  
##  <a name="setitem"></a>CComboBoxEx::SetItem  
 Bir öğeyi özniteliklerini ayarlar bir **ComboBoxEx** denetim.  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `pCBItem`  
 Bir işaretçi bir [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) madde bilgilerini alacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi ileti işlevselliğini uygulayan [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788), Windows SDK'ın açıklandığı gibi.  
  
##  <a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme  
 Görsel stilini Genişletilmiş Birleşik giriş kutusu denetimi ayarlar.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pszSubAppName`  
 Ayarlamak için Genişletilmiş Birleşik giriş kutusu görsel stil içeren bir Unicode dize için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi işlevselliğini öykünen [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) , Windows SDK'ın açıklandığı gibi ileti.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MFCIE](../../visual-cpp-samples.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)
