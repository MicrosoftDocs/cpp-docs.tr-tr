---
title: CMFCRibbonColorButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa188930f6fe80d26282252ef3aae875aa19922f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton sınıfı
`CMFCRibbonColorButton` Sınıfı bir Şerit çubuğuna ekleyebileceğiniz bir renk düğmesi uygular. Şerit renk düğmesi, bir veya daha fazla renk paletlerini içeren bir açılır menü görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Renkleri bir grup normal renk alanına ekler.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Belirtir olup olmadığını **otomatik** düğmesi etkindir.|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Etkinleştirir **diğer** düğmesi.|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|Seçili renk döndürür.|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Renk çubuğunda görünen rengi öğelerinin boyutunu döndürür.|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Seçili olan öğenin rengini açılan renk paletini temel döndürür.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Tüm renk grupları normal renk alanından kaldırır.|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|Bir renk normal renk alanından seçer.|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Görüntülenen tüm renk öğelerinin boyutunu renk çubuğunda ayarlar.|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Belge renk alanında görüntülemek için RGB değerleri listesini belirtir.|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>Açıklamalar  
 Bir kullanıcı bastığında Şerit renk düğmesi bir renk çubuğu görüntüler. Varsayılan olarak, bu renk çubuğu normal renk alanını adlı bir renk seçimi paletini içerir. İsteğe bağlı olarak, renk çubuğu görüntüleyebilirsiniz bir **otomatik** kullanıcının varsayılan renk seçmesine olanak tanıyan düğmesi ve bir **diğer** ek renkleri içeren bir açılır renk paleti görüntüler düğmesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCRibbonColorButton` sınıfı. Örnek nasıl oluşturulacağını gösterir bir `CMFCRibbonColorButton` nesne, büyük resmi ayarlama, etkinleştirme **otomatik** düğmesini tıklatın, etkinleştirmek **diğer** düğmesi, sütun sayısını ayarlayın, tüm renk öğelerinin boyutunu Ayarla renk çubuğunda görünür, normal renk alana renkleri grubu ekleyin ve belge renk alanında görüntülemek için RGB değerleri listesini belirtin. Bu kod parçacığını parçası olan [çizin istemci örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup  
 Renkleri bir grup normal renk alanına ekler.  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszName`  
 Grup adı.  
  
 [in] `lstColors`  
 Renk listesi.  
  
 [in] `bContiguousColumns`  
 Renk öğelerin grubunda nasıl görüntüleneceğini denetler. Varsa `TRUE`, renk öğeleri dikey boşluk olmadan çizilir. Varsa `FALSE`, renk öğeleri dikey bir aralık ile çizilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev Rengi açılır yapmak için kullanım renkleri birkaç grupları görüntüler. Renkleri grubunda görüntülenme biçimini kontrol edebilirsiniz.  
  
##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton  
 Oluşturan bir `CMFCRibbonColorButton` nesnesi.  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nID`  
 Bir kullanıcı düğmesine tıkladığında yürütülecek komut komut Kimliğini belirtir.  
  
 [in] `lpszText`  
 Düğmeyi görüntülenecek metni belirtir.  
  
 [in] `nSmallImageIndex`  
 Düğmeyi görünmesi küçük resim sıfır tabanlı dizini.  
  
 [in] `color`  
 (Varsayılan değeri siyah) düğmesini rengi.  
  
 [in] `bSimpleButtonLook`  
 Varsa `TRUE`, düğme basit bir dikdörtgen çizilir.  
  
 [in] `nLargeImageIndex`  
 Düğmeyi görünmesi büyük görüntü sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton  
 Belirtir olup olmadığını **otomatik** düğmesi etkindir.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszLabel`  
 Etiketi **otomatik** düğmesi.  
  
 [in] `colorAutomatic`  
 Belirten bir RGB değeri **otomatik** düğmenin varsayılan rengi.  
  
 [in] `bEnable`  
 `TRUE` varsa **otomatik** düğmesi etkin; `FALSE` devre dışı ise.  
  
 [in] `lpszToolTip`  
 Araç İpucu **otomatik** düğmesi.  
  
 [in] `bOnTop`  
 Belirtir olup olmadığını **otomatik** düğmesi olan renk paletini önce üst.  
  
 [in] `bDrawBorder`  
 `TRUE` Uygulama renk çubuğu çevresinde kenarlık Şerit renk düğmesi çizer durumunda. Şu anda seçili olan rengi renk çubuğu görüntüler. `FALSE` Uygulama kenarlık çekmek değil  
  
##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton  
 Etkinleştirir **diğer** düğmesi.  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszLabel`  
 Düğmenin etiketi.  
  
 `lpszToolTip`  
 Araç ipucu metnini **diğer** düğmesi.  
  
### <a name="remarks"></a>Açıklamalar  
 **Diğer** düğmesi olan renkleri grubu altında görüntülenen düğme. Kullanıcı tıkladığında **diğer** düğmesi, bir renk iletişim kutusu görüntüler.  
  
##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor  
 Geçerli otomatik düğme rengi alır.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli otomatik düğme rengi temsil eden bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik düğme rengi belirlediği `colorAutomatic` parametresi geçirilen `CMFCRibbonColorButton::EnableAutomaticButton` yöntemi.  
  
##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor  
 Seçili renk döndürür.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesine tıklayarak seçili rengi.  
  
##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize  
 Renk çubuğunda görünen rengi öğelerinin boyutunu döndürür.  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Renk düğmeler aşağı açılan renk paletindeki boyutu.  
  
##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns  
 Şerit renk düğmenin galeri görüntü satırda öğe sayısını alır.  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her satırda simgeler sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor  
 Seçili olan öğenin rengini açılır renk paletini temel döndürür.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Seçili olan öğenin açılır renk paletindeki rengi.  
  
##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups  
 Tüm renk grupları normal renk alanından kaldırır.  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor  
 Bir renk normal renk alanından seçer.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `color`  
 Ayarlamak için renk.  
  
##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize  
 Görüntülenen tüm renk öğelerinin boyutunu renk çubuğunda ayarlar.  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `sizeBox`  
 Renk paletindeki renk düğmeleri yeni boyutu.  
  
##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName  
 Belirli bir renk için yeni bir ad ayarlar.  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `color`  
 Bir renk RGB değeri.  
  
 [in] `strName`  
 Belirtilen renk için yeni ad.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırır çünkü `CMFCColorBar::SetColorName`, bu yöntem tüm belirtilen renk adını değiştirir `CMFCColorBar` uygulamanızdaki nesneleri.  
  
##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns  
 Kullanıcının renk seçimi işlemi sırasında kullanıcıya sunulan renk tablosundaki görüntülenen sütunların sayısını ayarlar.  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nColumns`  
 Her satırda görüntülemek için renk simgeler sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors  
 Belge renk alanında görüntülemek için RGB değerleri listesini belirtir.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszLabel`  
 Belge renklerle görüntülenecek metin.  
  
 [in] `lstColors`  
 RGB değerleri listesi başvuru.  
  
##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette  
 Renk düğmesi görüntüler renk tablosundaki görüntülemek için standart renklerini belirtir.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pPalette`  
 Renk paleti gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor  
 Kullanıcının kullanıcı renk düğmesini tıklattığında görüntülenen renk tablosundan bir renk seçtiğinde çerçevesi tarafından çağrılır.  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `color`  
 Kullanıcının seçtiği bir renk.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCRibbonColorButton::UpdateColor` Yöntemi şu anda seçili düğmenin rengi değişir ve kendi üst göndererek bildirir bir `WM_COMMAND` ile ileti bir `BN_CLICKED` standart bir bildirim. Kullanım [CMFCRibbonColorButton::GetColor](#getcolor) seçili renk alma yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Sınıfı](../../mfc/reference/cmfcribbongallery-class.md)
