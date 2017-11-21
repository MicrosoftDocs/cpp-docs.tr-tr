---
title: "CMFCToolBarFontSizeComboBox sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
dev_langs: C++
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0218d084dca2920cbf88a4cbfffa8215443be004
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox sınıfı
Yazı tipi boyutu seçmek kullanıcının sağlayan bir birleşik giriş kutusu denetimi içeren bir araç çubuğu düğmesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Oluşturan bir `CMFCToolBarFontSizeComboBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Seçili yazı tipi boyutu twips'lerle döndürür.|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Açılan kutu listesi belirtilen yazı tipi için tüm desteklenen yazı tipi boyutlarını doldurur.|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Yazı tipi boyutunu twip cinsinden ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz bir `CMFCToolBarFontSizeComboBox` nesnesi ile birlikte bir [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md) bir yazı tipi ve yazı tipi boyutu seçmek bir kullanıcı etkinleştirme nesnesi.  
  
 Yazı tipi birleşik giriş kutusu düğmesi eklediğiniz gibi bir araç çubuğuna bir yazı tipi boyutu birleşik giriş kutusu düğmesi ekleyebilirsiniz. Daha fazla bilgi için bkz: [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
 Kullanıcı yeni bir yazı tipi seçtiğinde bir `CMFCToolBarFontComboBox` nesne doldurabilirsiniz yazı tipi boyutu birleşik giriş kutusu, yazı tipi için desteklenen boyutlar ile kullanarak [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) yöntemi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCToolBarFontSizeComboBox` yapılandırmak için sınıf bir `CMFCToolBarFontSizeComboBox` nesnesi. Örnek metin kutusunda yazı tipi boyutunu twip almak, tüm geçerli verilen yazı tipi boyutlarıyla yazı tipi boyutu birleşik giriş kutusu doldurun ve twips'lerle yazı tipi boyutunu belirtmek nasıl gösterilmektedir. Bu kod parçacığını parçası olan [Word paneli örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontsizecombobox"></a>CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox  
 Oluşturan bir `CMFCToolBarFontSizeComboBox` nesnesi.  
  
```  
CMFCToolBarFontSizeComboBox();
```  
  
##  <a name="gettwipsize"></a>CMFCToolBarFontSizeComboBox::GetTwipSize  
 Yazı tipi boyutunu twip yazı tipi boyutu birleşik giriş kutusu metin kutusundan alır.  
  
```  
int GetTwipSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri pozitif ise twip yazı tipi boyutu.. Açılan kutunun metin kutusu boş ise -1 olur. Bir hata oluşursa, -2 var.  
  
##  <a name="rebuildfontsizes"></a>CMFCToolBarFontSizeComboBox::RebuildFontSizes  
 Yazı tipi boyutu birleşik giriş kutusu tüm geçerli verilen yazı tipi boyutlarını ile doldurur.  
  
```  
void RebuildFontSizes(const CString& strFontName);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] strFontName`  
 Yazı tipi adı belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yazı tipi birleşik giriş kutusu seçimde arasında bir yazı tipi boyutu birleşik giriş kutusu gibi eşitlemek için istediğiniz zaman bu işlev çağrısı bir [CMFCToolBarFontComboBox sınıfı](../../mfc/reference/cmfctoolbarfontcombobox-class.md).  
  
##  <a name="settwipsize"></a>CMFCToolBarFontSizeComboBox::SetTwipSize  
 Belirtilen yuvarlar (twips'lerle) noktaları ve ardından ayarlar yakın boyutu bu değeri açılan kutu seçilen boyutta boyutu.  
  
```  
void SetTwipSize(int nSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nSize`  
 Ayarlamak için yazı tipi boyutunu (twip) belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak, daha sonra bir önceki geçerli yazı tipi boyutunu alabilirsiniz [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton sınıfı](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo sınıfı](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [İzlenecek yol: Araç çubuklarına denetimler yerleştirme](../../mfc/walkthrough-putting-controls-on-toolbars.md)



