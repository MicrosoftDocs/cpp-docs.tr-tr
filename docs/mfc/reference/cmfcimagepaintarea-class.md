---
title: "CMFCImagePaintArea sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs: C++
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 70888bbd0acaef49bac67147bff4fe7719a84404
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea sınıfı
Görüntü Düzenleyicisi iletişim kutusunda bir görüntüsünü değiştirmek için kullanın resim alanı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Oluşturan bir `CMFCImagePaintArea` nesnesi.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCImagePaintArea::GetMode](#getmode)|Geçerli çizim modunu alır.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Resim alanı için bit eşlem resim ayarlar.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Geçerli çizim rengini belirler.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Geçerli çizim modu ayarlar.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
 Çerçeve resim alanı bir görüntü Düzenleyicisi iletişim kutusunda görüntülemek için bu sınıfı kullanır. Görüntü Düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için bkz: [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCImagePaintArea` sınıfı, renk çizim, geçerli çizim modu ayarlamak ve resim alanı için bit eşlem resim ayarlamak geçerli ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea  
 Oluşturan bir `CMFCImagePaintArea` nesnesi.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pParentDlg`|Görüntü Düzenleyicisi üst iletişim kutusu için bir işaretçi.|  
  
##  <a name="getmode"></a>CMFCImagePaintArea::GetMode  
 Geçerli çizim modunu alır.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [ımage_edıt_mode](cmfcimagepaintarea-image-edit-mode-enumeration.md) geçerli çizim modu belirten değer.  
  
##  <a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap  
 Resim alanı için bit eşlem resim ayarlar.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`pBitmap`|Görüntülenecek yeni bit eşlem resim.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `pBitmap` olan `NULL`, bu yöntem değiştirilebilir boyama alanının boyutunu sıfır olarak ayarlar. Aksi takdirde, sağlanan bit eşlem resim boyutunu değiştirilebilir boyama alanının boyutunu ayarlar.  
  
##  <a name="setcolor"></a>CMFCImagePaintArea::SetColor  
 Geçerli çizim rengini belirler.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`color`|Yeni Çizim rengi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman bir renk görüntü Düzenleyicisi palet çubuğundan seçin veya Renk Seçici, framework geçerli çizim renk güncelleştirmek için bu yöntemi çağırır. İlk çizim rengi siyah (bir `COLORREF` 0 değeri).  
  
 Çizim renk dışındaki tüm çizim modları için görüntü Düzenleyicisi iletişim kutusu tarafından kullanılan `IMAGE_EDIT_MODE_COLOR`. Çizim modları hakkında daha fazla bilgi için bkz: [Cmfcımagepaintarea::ımage_edıt_mode numaralandırması](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="setmode"></a>CMFCImagePaintArea::SetMode  
 Geçerli çizim modu ayarlar.  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in]`mode`|Bir [ımage_edıt_mode](cmfcimagepaintarea-image-edit-mode-enumeration.md) geçerli çizim modu belirten değer.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
