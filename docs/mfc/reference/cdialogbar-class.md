---
title: "CDialogBar sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs: C++
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5663d093022345036f623dd344bae738e0acf5eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdialogbar-class"></a>CDialogBar sınıfı
Denetim çubuğu Windows kalıcı olmayan iletişim kutusunda işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|Oluşturan bir `CDialogBar` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Bir Windows iletişim çubuğu oluşturur ve ona ekler `CDialogBar` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı arasında sekmesinde standart Windows denetimleri içerdiğinden, bir iletişim çubuğu bir iletişim kutusu benzer. Başka bir benzerlik iletişim çubuğu temsil etmek için bir iletişim şablonunu oluşturacağı açıklanmaktadır.  
  
 Oluşturma ve bir iletişim çubuğu kullanma oluşturma ve kullanma için benzer bir `CFormView` nesnesi. İlk olarak, kullanın [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md) stiliyle bir iletişim şablonunu tanımlamak için **WS_CHILD** ve başka bir stil. Şablon stili olmamalıdır **ws_vısıble**. Uygulama kodunuzda oluşturmak için oluşturucu çağrısı `CDialogBar` nesne sonra çağırın **oluşturma** iletişim çubuğu penceresi oluşturun ve ona eklemek için `CDialogBar` nesnesi.  
  
 Daha fazla bilgi için `CDialogBar`, makaleye bakın [iletişim kutusu çubukları](../../mfc/dialog-bars.md) ve [Teknik Not 31](../../mfc/tn031-control-bars.md), Denetim çubuklarını.  
  
> [!NOTE]
>  Geçerli sürümde, bir `CDialogBar` nesnesi Windows Forms denetimlerini barındıramaz. Visual C++'ta Windows Forms denetimleri hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanarak](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="cdialogbar"></a>CDialogBar::CDialogBar  
 Oluşturan bir `CDialogBar` nesnesi.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>CDialogBar::Create  
 İletişim kutusu kaynak şablonu tarafından belirtilen yükler `lpszTemplateName` veya `nIDTemplate`iletişim çubuğu pencere oluşturur, stilini ayarlar ve ile ilişkilendirir `CDialogBar` nesnesi.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `pParentWnd`  
 Üst için bir işaretçi `CWnd` nesnesi.  
  
 `lpszTemplateName`  
 Adını gösteren bir işaretçi `CDialogBar` nesnenin iletişim kutusu kaynak şablonu.  
  
 `nStyle`  
 Araç çubuğu stili. Desteklenen ek araç çubuğu stilleri şunlardır:  
  
- `CBRS_TOP`Denetim çubuğu çerçeve penceresi tepesinde bulunur.  
  
- `CBRS_BOTTOM`Denetim çubuğu çerçeve penceresinin alt kısmındaki ' dir.  
  
- `CBRS_NOALIGN`Üst yeniden boyutlandırıldığında denetim çubuğu yeniden konumlandırılır değil.  
  
- `CBRS_TOOLTIPS`Denetim çubuğu araç ipuçları görüntüler.  
  
- **Cbrs_sıze_dynamıc** denetim çubuğu dinamik.  
  
- **Cbrs_sıze_fıxed** denetim çubuğu sabittir.  
  
- **CBRS_FLOATING** denetim çubuğu kayan.  
  
- `CBRS_FLYBY`Durum çubuğu düğme hakkındaki bilgileri görüntüler.  
  
- **CBRS_HIDE_INPLACE** denetim çubuğu kullanıcıya görüntülenmez.  
  
 `nID`  
 İletişim çubuğu denetiminin kimliği.  
  
 `nIDTemplate`  
 Kaynak Kimliği `CDialogBar` nesnenin iletişim kutusu şablon.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtirseniz `CBRS_TOP` veya `CBRS_BOTTOM` hizalama Stili iletişim çubuğu genişliği, çerçeve penceresi ve yüksekliğini, tarafından belirtilen kaynak `nIDTemplate`. Belirtirseniz `CBRS_LEFT` veya `CBRS_RIGHT` hizalama Stili iletişim çubuğunun yüksekliği, çerçeve penceresi ve genişliğini, tarafından belirtilen kaynak `nIDTemplate`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Cformview'yu sınıfı](../../mfc/reference/cformview-class.md)   
 [CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
