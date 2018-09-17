---
title: Cmfcımagepaintarea sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::CMFCImagePaintArea
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::GetMode
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetBitmap
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetColor
- AFXIMAGEPAINTAREA/CMFCImagePaintArea::SetMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea [MFC], CMFCImagePaintArea
- CMFCImagePaintArea [MFC], GetMode
- CMFCImagePaintArea [MFC], SetBitmap
- CMFCImagePaintArea [MFC], SetColor
- CMFCImagePaintArea [MFC], SetMode
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee3bf6b087777bc550a34234a8969e2127c8ec2d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720258"
---
# <a name="cmfcimagepaintarea-class"></a>Cmfcımagepaintarea sınıfı
Bir Resim Düzenleyicisi iletişim kutusunu görüntüdeki değiştirmek için kullandığınız resim alanı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|Oluşturur bir `CMFCImagePaintArea` nesne.|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|Yıkıcı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCImagePaintArea::GetMode](#getmode)|Geçerli çizim modunu alır.|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|Bit eşlem görüntüsüne resim alanı için ayarlar.|  
|[CMFCImagePaintArea::SetColor](#setcolor)|Geçerli çizim rengini ayarlar.|  
|[CMFCImagePaintArea::SetMode](#setmode)|Geçerli çizim modu ayarlar.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf doğrudan sizin kodunuzdan kullanılmak üzere tasarlanmamıştır.  
  
 Çerçeve, resim alanı içinde bir Resim Düzenleyicisi iletişim kutusunu görüntülemek için bu sınıfı kullanır. Resim Düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCImagePaintArea` sınıfı, geçerli renk çizim, geçerli çizim modu ayarlamak ve resim alanı için bit eşlem resmi ayarlama ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#37](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [Cmfcımagepaintarea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afximagepaintarea.h  
  
##  <a name="cmfcimagepaintarea"></a>  CMFCImagePaintArea::CMFCImagePaintArea  
 Oluşturur bir `CMFCImagePaintArea` nesne.  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pParentDlg*|[in] Üst görüntü Düzenleyicisi iletişim kutusu için bir işaretçi.|  
  
##  <a name="getmode"></a>  CMFCImagePaintArea::GetMode  
 Geçerli çizim modunu alır.  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir [ımage_edıt_mode](cmfcimagepaintarea-image-edit-mode-enumeration.md) geçerli çizim modu belirten bir değer.  
  
##  <a name="setbitmap"></a>  CMFCImagePaintArea::SetBitmap  
 Bit eşlem görüntüsüne resim alanı için ayarlar.  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*pBitmap*|[in] Görüntülenecek yeni bit eşlem resim.|  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *pBitmap* NULL ise bu yöntem değiştirilebilir Boya alanın boyutu sıfır olarak ayarlıyor. Aksi takdirde, sağlanan bit eşlem görüntüsüne boyutunu değiştirilebilir Boya alanının boyutunu ayarlar.  
  
##  <a name="setcolor"></a>  CMFCImagePaintArea::SetColor  
 Geçerli çizim rengini ayarlar.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*Renk*|[in] Yeni Çizim rengi.|  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman bir renk Resim Düzenleyicisi palet çubuğundan seçin veya Renk Seçici, framework geçerli çizim rengini güncelleştirmek için bu yöntemi çağırır. İlk çizim rengi siyah (0 COLORREF değeri).  
  
 Çizim rengini IMAGE_EDIT_MODE_COLOR hariç tüm çizim modları için görüntü Düzenleyicisi iletişim kutusu tarafından kullanılır. Çizim modları hakkında daha fazla bilgi için bkz. [Cmfcımagepaintarea::ımage_edıt_mode numaralandırması](cmfcimagepaintarea-image-edit-mode-enumeration.md).  
  
##  <a name="setmode"></a>  CMFCImagePaintArea::SetMode  
 Geçerli çizim modu ayarlar.  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|*Modu*|[in] Bir [ımage_edıt_mode](cmfcimagepaintarea-image-edit-mode-enumeration.md) geçerli çizim modu belirten bir değer.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
