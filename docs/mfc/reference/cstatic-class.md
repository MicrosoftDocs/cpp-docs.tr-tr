---
title: CStatic sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
dev_langs:
- C++
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3b1a5dcfc8481727bffd8b80e0bb1b230d56ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cstatic-class"></a>CStatic sınıfı
Windows statik denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|Oluşturan bir `CStatic` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CStatic::Create](#create)|Windows statik denetimi oluşturur ve ona ekler `CStatic` nesnesi.|  
|[CStatic::DrawItem](#drawitem)|Sahip tarafından çizilmiş statik denetimi çizmek için geçersiz kılın.|  
|[CStatic::GetBitmap](#getbitmap)|İle önceden ayarlanmış bit eşlem işleyicisini alır [SetBitmap](#setbitmap).|  
|[CStatic::GetCursor](#getcursor)|İmleç görüntü tanıtıcısı önceden ayarlanmış ile alır [SetCursor](#setcursor).|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|İle önceden ayarlanmış geliştirilmiş meta dosyası işleyicisini alır [SetEnhMetaFile](#setenhmetafile).|  
|[CStatic::GetIcon](#geticon)|İle önceden ayarlanmış simgesi işleyicisini alır [SetIcon](#seticon).|  
|[CStatic::SetBitmap](#setbitmap)|Statik denetiminde görüntülenecek bir bit eşlem belirtir.|  
|[CStatic::SetCursor](#setcursor)|Statik denetiminde görüntülenecek imleç görüntü belirtir.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Statik denetiminde görüntülenecek bir Gelişmiş Meta dosyası belirtir.|  
|[CStatic::SetIcon](#seticon)|Statik denetiminde görüntülenecek bir simge belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Statik bir denetimi bir metin dizesi, kutusu, dikdörtgen, simge, imleç, bit eşlem veya Gelişmiş Meta dosyası görüntüler. Etiket, kutusunda veya diğer denetimleri ayırmak için kullanılabilir. Statik bir denetimi normalde hiçbir girdi alır ve çıktı sağlar; Ancak, ile oluşturulmuşsa, fare tıklamaları üst bildirebilir **ss_notıfy** stili.  
  
 Statik bir denetimi iki adımda oluşturun. İlk olarak, oluşturmak için oluşturucu çağrısı `CStatic` nesne sonra çağırın [oluşturma](#create) statik denetimi oluşturmak ve ona eklemek için üye işlevi `CStatic` nesnesi.  
  
 Oluşturursanız, bir `CStatic` nesnesi (aracılığıyla bir iletişim kutusu kaynağı), bir iletişim kutusu içinde `CStatic` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CStatic` nesne bir pencere içinde de gerekebilir, yok. A `CStatic` bir pencere içinde yığında oluşturulan nesne otomatik olarak yok. Oluşturursanız, `CStatic` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** ile bittiğinde yok etmek için nesne üzerinde.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="create"></a>  CStatic::Create  
 Windows statik denetimi oluşturur ve ona ekler `CStatic` nesnesi.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszText,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID = 0xffff);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszText`  
 Denetimde yerleştirmek için metni belirtir. Varsa **NULL**, metin görünür olur.  
  
 `dwStyle`  
 Statik denetimin pencere stili belirtir. Herhangi bir bileşimini uygulamak [statik denetim stilleri](../../mfc/reference/styles-used-by-mfc.md#static-styles) denetlemek için.  
  
 `rect`  
 Statik denetimi boyutunu ve konumunu belirtir. Ya da olabilir bir `RECT` yapısı veya `CRect` nesnesi.  
  
 `pParentWnd`  
 Belirtir `CStatic` ana penceresinde, genellikle bir `CDialog` nesnesi. Değil olmalıdır **NULL**.  
  
 `nID`  
 Statik denetimin denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CStatic` iki adımda nesne. İlk olarak, Oluşturucusu çağrısı `CStatic`ve ardından arama **Oluştur**, hangi Windows statik denetimi oluşturur ve ona ekler `CStatic` nesne.  
  
 Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) statik denetlemek için:  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
 Bir bitmap, imleç, simge veya meta dosyası statik denetiminde görüntüleme kullanacaksanız, aşağıdakilerden biri geçerli gerekir [statik stiller](../../mfc/reference/styles-used-by-mfc.md#static-styles):  
  
- **Ss_bıtmap** bu stili bit eşlemler için kullanın.  
  
- **Ss_ıcon** bu stili işaretçileri ve simgeleri kullanın.  
  
- **Ss_enhmetafıle** bu stili için geliştirilmiş meta dosyası kullanın.  
  
 İmleçler, bit eşlemler veya simgeleri için aşağıdaki stil kullanmak isteyebilirsiniz:  
  
- **Ss_centerımage** statik denetiminde görüntü merkezi için kullanın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>  CStatic::CStatic  
 Oluşturan bir `CStatic` nesnesi.  
  
```  
CStatic();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CStatic::DrawItem  
 Sahip tarafından çizilmiş statik denetimi çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpDrawItemStruct`  
 Bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) yapısı. Yapısı çizilecek madde ve gerekli çizim türü hakkındaki bilgileri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sahip tarafından çizilmiş için çizim uygulamak için bu işlevi geçersiz **CStatic** nesne (Denetim stilde **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>  CStatic::GetBitmap  
 İle önceden ayarlanmış bit eşlem işleyicisini alır [SetBitmap](#setbitmap), yani ilişkili `CStatic`.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bit eşlem için bir tanıtıcı veya **NULL** hiçbir bit eşlem ayarlarsanız.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>  CStatic::GetCursor  
 İle önceden ayarlanmış imleci işleyicisini alır [SetCursor](#setcursor), yani ilişkili `CStatic`.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli imleci için tanıtıcı veya **NULL** hiçbir imleç ayarlarsanız.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile  
 İle önceden ayarlanmış geliştirilmiş meta dosyası işleyicisini alır [SetEnhMetafile](#setenhmetafile), yani ilişkili `CStatic`.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Gelişmiş Meta dosyası için bir tanıtıcı veya **NULL** hiçbir geliştirilmiş meta dosyası ayarlarsanız.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>  CStatic::GetIcon  
 İle önceden ayarlanmış simgesi işleyicisini alır [SetIcon](#seticon), yani ilişkili `CStatic`.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tanıtıcı geçerli simgesine veya **NULL** hiçbir simge ayarlarsanız.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>  CStatic::SetBitmap  
 Yeni bir bitmap statik denetimi ile ilişkilendirir.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
 `hBitmap`  
 Statik denetiminde çizilecek bit eşlem tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce statik denetimi ile ilişkili bit eşlem tanıtıcısı veya `NULL` hiçbir bit eşlem statik denetimi ile ilişkili ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit eşlem statik denetimde otomatik olarak çizilir. Varsayılan olarak, sol üst köşede çizilecek ve statik denetimi bit eşlem boyutunu boyutlandırılır.  
  
 Çeşitli penceresi ve statik denetim stilleri, aşağıdakiler dahil olmak üzere kullanabilirsiniz:  
  
-   Ss_bıtmap bu stili her zaman için bit eşlemler kullanın.  
  
-   Ss_centerımage statik denetiminde görüntü merkezi için kullanın. Görüntü statik denetimden daha büyükse kırpılır. Statik denetimden küçükse, bit eşlem sol üst köşesindeki piksel rengi tarafından görüntünün çevresine boş alanı doldurulur.  
  
-   MFC sınıf sağlar `CBitmap`, bir bit eşlem görüntü yalnızca Win32 çağrısı daha fazla işlev olduğunda kullanabileceğiniz `LoadBitmap`. `CBitmap`, bir tür GDI nesnesi içeren Sık kullanılan işbirliği içinde `CStatic`, olduğu bir `CWnd` grafik nesnesi statik bir denetim olarak görüntülemek için kullanılan sınıf.  
  
 `CImage` Daha fazla kolayca aygıt bağımsız bit eşlemler (DIB) çalışmanıza imkan tanıyan bir ATL/MFC sınıftır. Daha fazla bilgi için bkz: [Cımage sınıfı](../../atl-mfc-shared/reference/cimage-class.md).  
  
-   Genel kullanımdır vermek için `CStatic::SetBitmap` HBITMAP operatör tarafından döndürülen GDI nesnesi bir `CBitmap` veya `CImage` nesnesi. Bunu yapmak için kod aşağıdaki satırı benzer.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
Aşağıdaki örnekte iki oluşturur `CStatic` yığında nesneleri. Ardından bir bit eşlem kullanarak bir sistem yüklerken `CBitmap::LoadOEMBitmap` ve diğer kullanarak bir dosyaya `CImage::Load`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>  CStatic::SetCursor  
 Yeni bir imleç görüntüsü statik denetimi ile ilişkilendirir.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>Parametreler  
 `hCursor`  
 Statik denetiminde çizilecek imleci tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce statik denetimle ilişkili imleci tanıtıcısı veya **NULL** hiçbir imleç statik denetimi ile ilişkili ise.  
  
### <a name="remarks"></a>Açıklamalar  
 İmleç statik denetimde otomatik olarak çizilir. Varsayılan olarak, sol üst köşede çizilecek ve statik denetimi imleci boyutunu boyutlandırılır.  
  
 Çeşitli penceresi ve statik denetim stilleri, aşağıdakiler de dahil olmak üzere kullanabilirsiniz:  
  
- **Ss_ıcon** bu stili her zaman işaretçileri ve simgeleri kullanın.  
  
- **Ss_centerımage** statik denetiminde merkezi için kullanın. Görüntü statik denetimden daha büyükse kırpılır. Statik denetimden küçükse, görüntünün çevresine boş alanı statik denetim arka plan rengiyle doldurulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile  
 Yeni bir Gelişmiş Meta dosyası görüntüsü statik denetimi ile ilişkilendirir.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>Parametreler  
 `hMetaFile`  
 Statik denetiminde çizilecek geliştirilmiş meta dosyası tanıtıcısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce statik denetimle ilişkili geliştirilmiş meta dosyası tanıtıcısı veya **NULL** hiçbir geliştirilmiş meta dosyası statik denetimi ile ilişkili ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Geliştirilmiş Meta dosyası statik denetimde otomatik olarak çizilir. Geliştirilmiş Meta dosyası statik denetimi boyutuna uyacak şekilde ölçeklendirilir.  
  
 Çeşitli penceresi ve statik denetim stilleri, aşağıdakiler de dahil olmak üzere kullanabilirsiniz:  
  
- **Ss_enhmetafıle** bu stili her zaman için geliştirilmiş meta dosyası kullanın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>  CStatic::SetIcon  
 Yeni bir simge görüntüsü statik denetimi ile ilişkilendirir.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>Parametreler  
 `hIcon`  
 Statik denetiminde çizilecek simgesinin işleci.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce statik denetimle ilişkili simgeyi tanıtıcısı veya **NULL** hiçbir simge statik denetimi ile ilişkili ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Simge statik denetimde otomatik olarak çizilir. Varsayılan olarak, sol üst köşede çizilecek ve statik denetimi simge boyutuna boyutlandırılır.  
  
 Çeşitli penceresi ve statik denetim stilleri, aşağıdakiler de dahil olmak üzere kullanabilirsiniz:  
  
- **Ss_ıcon** bu stili her zaman işaretçileri ve simgeleri kullanın.  
  
- **Ss_centerımage** statik denetiminde merkezi için kullanın. Görüntü statik denetimden daha büyükse kırpılır. Statik denetimden küçükse, görüntünün çevresine boş alanı statik denetim arka plan rengiyle doldurulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [CButton sınıfı](../../mfc/reference/cbutton-class.md)   
 [CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)   
 [CEdit sınıfı](../../mfc/reference/cedit-class.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [CScrollBar sınıfı](../../mfc/reference/cscrollbar-class.md)   
 [CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
