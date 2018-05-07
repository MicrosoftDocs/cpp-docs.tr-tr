---
title: CMFCImageEditorDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 795e5548e93323af389c3faeaefa7dda0bf7d80c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog sınıfı
`CMFCImageEditorDialog` Sınıfı, bir görüntü Düzenleyicisi iletişim kutusu destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|Oluşturan bir `CMFCImageEditorDialog` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMFCImageEditorDialog` Sınıfı içeren bir iletişim kutusu sağlar:  
  
-   Tek tek piksel cinsinden görüntü değiştirmek için kullandığınız bir resim alanı.  
  
-   Çizim Araçları piksel cinsinden resim alanı değiştirmek için.  
  
-   Çizim araçları tarafından kullanılan rengi belirlemek için bir renk paleti.  
  
-   Önizleme alanı düzenlemeniz etkisini görüntüler.  
  
 Aşağıdaki çizimde bir görüntü Düzenleyicisi iletişim kutusu gösterir.  
  
 ![CMFCImageEditorDialog iletişim kutusu](../../mfc/reference/media/imageedit.png "imageedit")  
  
 Kullanmak için tek yönlü bir `CMFCImageEditorDialog` nesnesidir geçirileceğini bir `CBitmap` düzenlenmesi görüntü. Büyük bir görüntü, alanı düzenleme görüntünün sınırlı bir boyutu vardır ve mantıksal piksel boyutu alanına uyacak şekilde ayarlanmış olduğundan oluşturmayın. Çağrı `DoModal` yöntemi bir modal iletişim kutusunu başlatın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afximageeditordialog.h  
  
##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog  
 Oluşturan bir `CMFCImageEditorDialog` nesnesi.  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>Parametreler  
 `pBitmap`  
 Bir görüntü işaretçi.  
  
 `pParent`  
 Geçerli görüntü Düzenleyicisi iletişim kutusunun üst pencere işaretçi.  
  
 `nBitsPixel`  
 Renk derinliği da adlandırılır tek bir piksel rengi temsil etmek için kullanılan bit sayısını.  Varsa `nBitsPixel` parametre -1, renk derinliği tarafından belirtilen görüntü türetilir `pBitmap` parametresi. Varsayılan değer -1'dir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görüntüyü değiştirmek için bir görüntü işaretçi geçirin `CMFCImageEditorDialog` Oluşturucusu. ' I çağırın `DoModal` modal bir iletişim kutusu açmak için yöntem. Zaman `DoModal` yöntemi döndürür, bit eşlem yeni görüntüyü içerir.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCImageEditorDialog` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
