---
title: "CMFCCaptionBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
dev_langs: C++
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4449ebd1563fe02705913fd4f19e51d195b3d732
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar sınıfı
A `CMFCCaptionBar` nesnesidir üç öğe görüntüleyen bir denetim çubuğu: düğme, bir metin etiketi ve bir bit eşlem. Bu gibi durumlarda, her tür bir öğe yalnızca aynı anda görüntüleyebilirsiniz. Her öğe denetiminin sol veya sağ kenarları veya merkezi hale getirebilirsiniz. Düz veya 3B stili başlık çubuğunun üst ve alt kenarlık için de uygulayabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|Başlık çubuğu denetimi oluşturur ve ona ekler `CMFCCaptionBar` nesnesi.|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Başka bir bölme dinamik olarak başlık çubuğunu ve üst çerçevesini arasında eklenebilir olup olmadığını gösterir. (Geçersiz kılmaları [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|Etkinleştirir veya başlık çubuğu düğmesini devre dışı bırakır.|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|Belirtilen öğenin döndürür.|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|Başlık çubuğunun kenarlık boyutu döndürür.|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|Başlık çubuğunda düğmesinin sınırlayıcı dikdörtgenini alır.|  
|[CMFCCaptionBar::GetMargin](#getmargin)|Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetim kenar arasındaki uzaklığı döndürür.|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|Başlık çubuğu ileti çubuğu modunda olup olmadığını belirtir.|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|Bit eşlem resim Başlık Çubuğu'ndan kaldırır.|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|Düğmenin resim yazısı çubuğundan kaldırır.|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|Başlık Çubuğu'ndan simgesini kaldırır.|  
|[CMFCCaptionBar::RemoveText](#removetext)|Metin etiketi Başlık Çubuğu'ndan kaldırır.|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|Bit eşlem resim başlık çubuğu için ayarlar.|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|Başlık çubuğunun kenarlık boyutunu ayarlar.|  
|[CMFCCaptionBar::SetButton](#setbutton)|Başlık çubuğu düğme ayarlar.|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|Düğmenin basılmış kalıp kalmayacağını belirtir.|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|Düğme için araç ipucu ayarlar.|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|Başlık çubuğu kenarlık stilini ayarlar.|  
|[CMFCCaptionBar::SetIcon](#seticon)|Başlık çubuğu simgesi ayarlar.|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|Başlık çubuğu için görüntü için araç ipucu ayarlar.|  
|[CMFCCaptionBar::SetMargin](#setmargin)|Başlık çubuğu öğesi kenarı ve başlık çubuğu denetim kenar arasındaki uzaklığı ayarlar.|  
|[CMFCCaptionBar::SetText](#settext)|Başlık çubuğunu metin etiketini ayarlar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|Başlık çubuğunun arka doldurmak için çerçevesi tarafından çağrılır.|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|Başlık çubuğunun kenarlık çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|Başlık çubuğu düğme çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|Başlık çubuğu resmi çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|Başlık çubuğu metni çizmek için çerçevesi tarafından çağrılır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|Başlık çubuğu arka plan rengi.|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|Başlık çubuğunun kenarlık rengi.|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|Başlık çubuğu metin rengi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Başlık çubuğu oluşturmak için aşağıdaki adımları izleyin:  
  
1.  Oluşturmak `CMFCCaptionBar` nesnesi. Genellikle, bir çerçeve pencere sınıfı başlık çubuğunu eklersiniz.  
  
2.  Çağrı [CMFCCaptionBar::Create](#create) başlık çubuğu denetimi oluşturmak ve ona eklemek için yöntemi `CMFCCaptionBar` nesnesi.  
  
3.  Çağrı [CMFCCaptionBar::SetButton](#setbutton), [CMFCCaptionBar::SetText](#settext), [CMFCCaptionBar::SetIcon](#seticon), ve [CMFCCaptionBar::SetBitmap](#setbitmap)başlık çubuğu öğeleri ayarlamak için.  
  
 Düğme öğesi ayarladığınızda, düğme komut kimliği atamanız gerekir. Kullanıcı, başlık çubuğu yollar düğmesine tıkladığında `WM_COMMAND` bu kimliği için üst çerçeve pencere iletileri.  
  
 Başlık çubuğu, Microsoft Office 2007 uygulamalarında görüntülenen ileti çubuğu öykünür ileti çubuğu modunda da çalışabilir. İleti çubuğu modunda başlık çubuğu, bir bit eşlem, bir ileti ve (genellikle bir iletişim kutusunu açar.) bir düğmesi görüntüler. Bit eşlem için bir araç ipucu atayabilirsiniz.  
  
 İleti çubuğu modunu etkinleştirmek için arama [CMFCCaptionBar::Create](#create) ve dördüncü parametrenin (bIsMessageBarMode) kümesine `TRUE`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCCaptionBar` sınıfı. Örnek başlık çubuğu denetim oluşturmak, 3B kenarlık başlık çubuğunun ayarlama, başlık çubuğu öğeleri kenarıyla başlık çubuğu denetim kenar arasındaki piksel cinsinden uzaklığı ayarlayın, başlık çubuğu düğme ayarlamak nasıl gösterir , düğmesi için araç ipucu başlık çubuğunu metin etiketi ayarlayın, başlık çubuğu için bit eşlem resmi ayarlama ve görüntü için araç ipucu başlık çubuğunda ayarlayın. Bu kod parçacığını parçası olan [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcaptionbar.h  
  
##  <a name="create"></a>CMFCCaptionBar::Create  
 Başlık çubuğu denetimi oluşturur ve ona ekler `CMFCCaptionBar` nesnesi.  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Mantıksal OR birleşimi başlık çubuğu stilleri.  
  
 `pParentWnd`  
 Başlık çubuğu denetiminin üst pencere.  
  
 `uID`  
 Başlık çubuğu denetiminin kimliği.  
  
 `nHeight`  
 Başlık çubuğu denetiminin piksel cinsinden yüksekliği. -1 olması durumunda yüksekliği simgesi, metin ve resim yazısı çubuğu denetimi görüntüler düğmesini yüksekliğini göre hesaplanır.  
  
 `bIsMessageBarMode`  
 `TRUE`Başlık çubuğunu ileti çubuğu modundaysa, `FALSE` Aksi takdirde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Başlık çubuğu denetimi başarıyla oluşturulduysa; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CMFCCaptionBar` iki adımda nesne. İlk Oluşturucusu arayın ve ardından, çağıran `Create` Windows denetimi oluşturup ekleninceye yöntemi `CMFCCaptionBar` nesnesi.  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 Başka bir bölme dinamik olarak başlık çubuğunu ve üst çerçevesini arasında eklenebilir olup olmadığını gösterir.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `FALSE` geçersiz kılınmadığı sürece.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 Etkinleştirir veya başlık çubuğu düğmesini devre dışı bırakır.  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bEnable`  
 `TRUE`düğmesini etkinleştirmek için `FALSE` düğmesini devre dışı bırakmak için.  
  
##  <a name="getalignment"></a>CMFCCaptionBar::GetAlignment  
 Belirtilen öğenin döndürür.  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`elem`  
 Hizalama alınacağı için bir başlık çubuğu öğesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir düğme, bir bit eşlem, metin veya simge gibi bir öğe hizalaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğenin şu değerlerden biri olabilir:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 Başlık çubuğunun kenarlık boyutu döndürür.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kenarlığın piksel cinsinden boyutu.  
  
##  <a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 Başlık çubuğunda düğmesinin sınırlayıcı dikdörtgenini alır.  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CRect` başlık çubuğunda düğmesinin sınırlayıcı dikdörtgenini koordinatlarını içeren nesne.  
  
##  <a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetim kenar arasındaki uzaklığı döndürür.  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetim kenar arasındaki piksel cinsinden uzaklığı.  
  
##  <a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 Başlık çubuğu ileti çubuğu modunda olup olmadığını belirtir.  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE`Başlık çubuğunu ileti çubuğu modundaysa, `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 İleti çubuğu modunda başlık çubuğunda bir araç ipucu, ileti metnini ve bir düğme görüntüyle görüntüler.  
  
##  <a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 Başlık çubuğu arka plan rengi.  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 Başlık çubuğunun kenarlık rengi.  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 Başlık çubuğu metin rengi.  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 Başlık çubuğunun arka doldurmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Başlık çubuğunun cihaz bağlamı için bir işaretçi.  
  
 [in]`rect`  
 Doldurmak için sınırlayıcı dikdörtgenini.  
  
### <a name="remarks"></a>Açıklamalar  
 `OnDrawBackground` Yöntemi başlık çubuğunun arka plan hakkında doldurulacak olduğunda çağrılır. Varsayılan uygulama arka kullanarak doldurur [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground) rengi.  
  
 Bu yöntemi geçersiz kılın bir `CMFCCaptionBar` türetilmiş başlık çubuğunun görünümünü özelleştirmek için sınıf.  
  
##  <a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 Başlık çubuğunun kenarlık çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Kenarlıkları görüntülemek için kullanılan bir cihaz bağlamı.  
  
 [in]`rect`  
 Sınırlayıcı dikdörtgenini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, kenarlıklar düz stil sahiptir.  
  
 Bu yöntemi geçersiz kılın bir `CMFCCaptionBar` türetilmiş başlık çubuğunun kenarlık görünümünü özelleştirmek için sınıf.  
  
##  <a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 Başlık çubuğu düğme çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Düğme görüntülemek için kullanılan bir cihaz bağlamı için bir işaretçi.  
  
 [in]`rect`  
 Düğmenin sınırlayıcı dikdörtgenini.  
  
 [in]`strButton`  
 Düğmenin metin etiketi.  
  
 [in]`bEnabled`  
 `TRUE`düğmesi etkinleştirilir `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi geçersiz kılın bir `CMFCCaptionBar` türetilmiş başlık çubuğu düğme görünümünü özelleştirmek için sınıf.  
  
##  <a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 Başlık çubuğu resmi çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Görüntüyü görüntülemek için kullanılan bir cihaz bağlamı için bir işaretçi.  
  
 [in]`rect`  
 Görüntünün sınırlayıcı dikdörtgenini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi geçersiz kılın bir `CMFCCaptionBar` türetilmiş resim görünümünü özelleştirmek için sınıf.  
  
##  <a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 Başlık çubuğu metni çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pDC`  
 Düğme görüntülemek için kullanılan bir cihaz bağlamı için bir işaretçi.  
  
 [in]`rect`  
 Metnin sınırlayıcı dikdörtgenini.  
  
 [in]`strText`  
 Görüntülenecek metin dizesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama kullanarak metin görüntüler `CDC::DrawText` ve [CMFCCaptionBar::m_clrBarText](#m_clrbartext) rengi.  
  
 Bu yöntemi geçersiz kılın bir `CMFCCaptionBar` türetilmiş başlık çubuğunun metin görünümünü özelleştirmek için sınıf.  
  
##  <a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 Bit eşlem resim Başlık Çubuğu'ndan kaldırır.  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 Düğmenin resim yazısı çubuğundan kaldırır.  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlık çubuğu öğeleri düzenini ayarlanmış otomatik olarak.  
  
##  <a name="removeicon"></a>CMFCCaptionBar::RemoveIcon  
 Başlık Çubuğu'ndan simgesini kaldırır.  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>CMFCCaptionBar::RemoveText  
 Metin etiketi Başlık Çubuğu'ndan kaldırır.  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>CMFCCaptionBar::SetBitmap  
 Bit eşlem resim başlık çubuğu için ayarlar.  
  
```  
void SetBitmap(
    HBITMAP hBitmap,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

 
void SetBitmap(
    UINT uiBmpResID,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hBitmap`  
 Ayarlamak için bit eşlem için tanıtıcı.  
  
 [in]`clrTransparent`  
 Bit eşlem saydam rengini belirtir bir RGB değeri.  
  
 [in]`bStretch`  
 Varsa `TRUE`, bit eşlem dikdörtgen sınırlayıcı görüntünün sığmadığında genişletilir. Aksi takdirde bit eşlem genişletilir değil.  
  
 [in]`bmpAlignment`  
 Bit eşlem hizalaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlık çubuğunda bir bit eşlem ayarlamak için bu yöntemi kullanın.  
  
 Önceki bit eşlem otomatik olarak yok. Aradığınız çünkü başlık çubuğunu simge görüntüler [CMFCCaptionBar::SetIcon](#seticon) yöntemini çağırarak simgesi kaldırmadığınız sürece bit eşlem görüntülenmez [CMFCCaptionBar::RemoveIcon](#removeicon).  
  
 Bit eşlem hizalanır belirtildiği gibi `bmpAlignment` parametresi.  Bu parametre şunlardan biri olabilir `BarElementAlignment` değerler:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 Başlık çubuğunun kenarlık boyutunu ayarlar.  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nSize`  
 Yeni boyutu, başlık çubuğu kenarlığının piksel cinsinden.  
  
##  <a name="setbutton"></a>CMFCCaptionBar::SetButton  
 Başlık çubuğu düğme ayarlar.  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszLabel`  
 Düğmenin komut etiketi.  
  
 `uiCmdUI`  
 Düğmenin komut kimliği.  
  
 `btnAlignmnet`  
 Düğmenin hizalaması.  
  
 `bHasDropDownArrow`  
 `TRUE`Düğme açılan ok, görüntülerse `FALSE` Aksi takdirde.  
  
##  <a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 Düğmenin basılmış kalıp kalmayacağını belirtir.  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bPresed`  
 `TRUE`düğmenin basılmış durumuna tutar, `FALSE` Aksi takdirde.  
  
##  <a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip  
 Düğme için araç ipucu ayarlar.  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszToolTip`  
 Araç İpucu açıklamalı alt yazı.  
  
 [in]`lpszDescription`  
 Araç İpucu açıklaması.  
  
##  <a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder  
 Başlık çubuğu kenarlık stilini ayarlar.  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`bFlat`  
 `TRUE`başlık çubuğunun kenarlık düz ise. `FALSE`3B kenarlık olması durumunda.  
  
##  <a name="seticon"></a>CMFCCaptionBar::SetIcon  
 Başlık çubuğu simgesi ayarlar.  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`hIcon`  
 Ayarlanacak simgesine işleci.  
  
 [in]`iconAlignment`  
 Simge hizalaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Başlık çubukları simgeler veya bit eşlemler görüntüleyebilirsiniz. Bkz: [CMFCCaptionBar::SetBitmap](#setbitmap) bir bit eşlem görüntülemek nasıl öğrenmek için. Hem simge hem de bit eşlem ayarlarsanız, simgeyi her zaman görüntülenir. Çağrı [CMFCCaptionBar::RemoveIcon](#removeicon) simge Başlık Çubuğu'ndan kaldırmak için.  
  
 Simge göre hizalanır `iconAlignment` parametresi. Şunlardan biri olabilir `BarElementAlignment` değerler:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
 Görüntü için araç ipucu başlık çubuğunda ayarlar.  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`lpszToolTip`  
 Araç İpucu metni.  
  
 [in]`lpszDescription`  
 Araç İpucu açıklaması.  
  
##  <a name="setmargin"></a>CMFCCaptionBar::SetMargin  
 Başlık çubuğu öğesi kenarı ve başlık çubuğu denetim kenar arasındaki uzaklığı ayarlar.  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nMargin`  
 Başlık çubuğu öğelerinin kenarı ve başlık çubuğu denetim kenar arasındaki piksel cinsinden uzaklığı.  
  
##  <a name="settext"></a>CMFCCaptionBar::SetText  
 Başlık çubuğunu metin etiketini ayarlar.  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`strText`  
 Ayarlamak için metin dizesi.  
  
 [in]`textAlignment`  
 Metin hizalaması.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin etiketi hizalanır belirtildiği gibi `textAlignment` parametresi. Şunlardan biri olabilir `BarElementAlignment` değerler:  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)
