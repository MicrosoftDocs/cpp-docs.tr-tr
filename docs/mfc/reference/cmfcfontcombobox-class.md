---
title: CMFCFontComboBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9141dec6fdcb966dcdb664bb8dc090b50a10a614
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040005"
---
# <a name="cmfcfontcombobox-class"></a>CMFCFontComboBox sınıfı
`CMFCFontComboBox` Sınıfı yazı tipleri listesini içeren bir birleşik giriş kutusu denetimi oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Oluşturan bir `CMFCFontComboBox` nesnesi.|  
|`CMFCFontComboBox::~CMFCFontComboBox`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCFontComboBox::CompareItem`|Geçerli yazı tipi birleşik giriş kutusu denetiminin sıralı liste kutusunda yeni bir öğe göreli konumunu belirlemek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|  
|`CMFCFontComboBox::DrawItem`|Geçerli yazı tipi birleşik giriş kutusu denetiminde belirli bir öğeyi çizmek için çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|  
|[CMFCFontComboBox::GetSelFont](#getselfont)|Şu anda seçili yazı tipi ilgili bilgileri alır.|  
|`CMFCFontComboBox::MeasureItem`|Geçerli yazı tipi birleşik giriş kutusu denetimi liste kutusunda boyutlarının Windows'a bildirmek için framework tarafından çağrılır. (Geçersiz kılmaları [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|  
|`CMFCFontComboBox::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCFontComboBox::SelectFont](#selectfont)|Yazı tipi açılan kutusundan belirtilen ölçütlere uyan yazıtipi seçer.|  
|[CMFCFontComboBox::Setup](#setup)|Yazı tipi birleşik giriş kutusu öğeleri listesini başlatır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Framework geçerli yazı tipi açılan kutuda öğe etiketlerini çizmek için kullanılacak yazı tipini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılacak bir `CMFCFontComboBox` nesne iletişim kutusunda, eklemek bir `CMFCFontComboBox` iletişim kutusu sınıfı için değişken. Ardından `OnInitDialog` yöntemi çağrısı iletişim kutusu sınıfı [CMFCFontComboBox::Setup](#setup) yöntemi birleşik giriş kutusu denetiminde öğe listesi başlatılamadı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxfontcombobox.h  
  
##  <a name="cmfcfontcombobox"></a>  CMFCFontComboBox::CMFCFontComboBox  
 Oluşturan bir `CMFCFontComboBox` nesnesi.  
  
```  
CMFCFontComboBox();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getselfont"></a>  CMFCFontComboBox::GetSelFont  
 Şu anda seçili yazı tipi ilgili bilgileri alır.  
  
```  
CMFCFontInfo* GetSelFont() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi [CMFCFontInfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md) bir yazı tipi tanımlar nesnesi. Bu olabilir `NULL` yazı tipi açılan kutuda seçtiyseniz.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_bdrawusingfont"></a>  CMFCFontComboBox::m_bDrawUsingFont  
 Framework geçerli yazı tipi açılan kutuda öğe etiketlerini çizmek için kullanılacak yazı tipini belirtir.  
  
```  
static BOOL m_bDrawUsingFont;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye kümesine `TRUE` her öğe etiketi çizmek için aynı yazı tipi kullanmaya framework yönlendirmek için. Bu üye kümesine `FALSE` her öğe etiketi adı etiketi ile aynı olan yazı tipiyle çizmek için framework yönlendirmek için. Bu üye varsayılan değeri `FALSE`.  
  
##  <a name="selectfont"></a>  CMFCFontComboBox::SelectFont  
 Yazı tipi açılan kutusundan belirtilen ölçütlere uyan yazıtipi seçer.  
  
```  
BOOL SelectFont(CMFCFontInfo* pDesc);

 
BOOL SelectFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDesc*  
 Yazı tipi açıklaması nesnesine noktaları.  
  
 [in] *lpszName*  
 Yazı tipi adı belirtir.  
  
 [in] *nCharSet*  
 Bir karakter kümesini belirtir. DEFAULT_CHARSET varsayılan değerdir. Daha fazla bilgi için bkz: `lfCharSet` üyesi [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yazı tipi açılan kutusunda bir öğe belirtilen yazı tipi açıklaması nesnesine veya yazı tipi adı ve charset eşleşirse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Seçin ve belirtilen yazı tipi için karşılık gelen yazı tipi birleşik giriş kutusu öğesi kaydırma için bu yöntemi kullanın.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `SelectFont` yönteminde `CMFCFontComboBox` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]  
  
##  <a name="setup"></a>  CMFCFontComboBox::Setup  
 Yazı tipi birleşik giriş kutusu öğeleri listesini başlatır.  
  
```  
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nFontType*  
 Yazı tipini belirtir. Varsayılan değer Bitsel (veya) DEVICE_FONTTYPE, RASTER_FONTTYPE ve TRUETYPE_FONTTYPE birleşimidir.  
  
 [in] *nCharSet*  
 Yazı tipi karakter kümesini belirtir. DEFAULT_CHARSET varsayılan değerdir.  
  
 [in] *nPitchAndFamily*  
 Aile ve yazı tipi aralığı belirtir. DEFAULT_PITCH varsayılan değerdir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yazı tipi birleşik giriş kutusu başarıyla başlatıldı Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, belirtilen parametrelerle eşleşen yüklü yazı tiplerini numaralandırma ve bu yazı tipi adlarını yazı tipi açılan kutuda ekleme yazı tipi birleşik giriş kutusu başlatır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `Setup` yönteminde `CMFCFontComboBox` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo Sınıfı](../../mfc/reference/cmfcfontinfo-class.md)
