---
title: CDialogBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ff69a4974cd85471b0cfa039f32ee0c1a76f82a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336390"
---
# <a name="cdialogbar-class"></a>CDialogBar sınıfı
Bir denetim çubuğundaki Windows modsuz iletişim kutusu işlevlerini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|Oluşturur bir `CDialogBar` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Bir Windows iletişim kutusu oluşturur ve ona ekler `CDialogBar` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı arasında sekme standart Windows denetimleri içeren, bir iletişim çubuğu bir iletişim kutusu benzer. Başka bir benzerlik iletişim çubuğu temsil etmek için bir iletişim şablonunu oluşturma ' dir.  
  
 Oluşturma ve bir iletişim çubuğu kullanma oluşturma ve kullanma için benzer bir `CFormView` nesne. İlk olarak, [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md) WS_CHILD stiliyle bir iletişim şablonunu ve başka bir stil tanımlamak için. Şablon stili ws_vısıble olmaması gerekir. Uygulama kodunuzda oluşturmak için oluşturucu çağrısı `CDialogBar` nesnesi ve ardından arama `Create` iletişim çubuğu penceresi oluştur ve buna eklemek için `CDialogBar` nesne.  
  
 Daha fazla bilgi için `CDialogBar`, makaleye göz atın [iletişim kutusu çubukları](../../mfc/dialog-bars.md) ve [Teknik Not 31](../../mfc/tn031-control-bars.md), Denetim çubukları.  
  
> [!NOTE]
>  Geçerli sürümde, bir `CDialogBar` nesne, Windows Forms denetimleri barındıramaz. Visual C++'ta Windows Forms denetimleri hakkında daha fazla bilgi için bkz: [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxext.h  
  
##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar  
 Oluşturur bir `CDialogBar` nesne.  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>  CDialogBar::Create  
 Tarafından belirtilen iletişim kutusu kaynak şablonu yükler `lpszTemplateName` veya `nIDTemplate`, iletişim çubuğu penceresi oluşturur, stilini ayarlar ve onunla ilişkilendirir `CDialogBar` nesne.  
  
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
 *pParentWnd*  
 Üst öğeye bir işaretçi `CWnd` nesne.  
  
 *lpszTemplateName*  
 Adı bir işaretçiye `CDialogBar` nesnenin iletişim kutusu kaynak şablonu.  
  
 *nStyle*  
 Araç çubuğu stili. Desteklenen ek toolbar stilleri şunlardır:  
  
- Çerçeve penceresinin üst kısmındaki CBRS_TOP denetim çubuğudur.  
  
- Çerçeve penceresinin alt kısmında CBRS_BOTTOM denetim çubuğu bulunmaktadır.  
  
- Üst yeniden boyutlandırıldığında CBRS_NOALIGN denetim çubuğu yeniden konumlandırıldığında değil.  
  
- Cbrs_tooltıps denetim çubuğunun araç ipuçlarını gösterir.  
  
- Cbrs_sıze_dynamıc denetim çubuğu dinamiktir.  
  
- Cbrs_sıze_fıxed denetim çubuğu sabittir.  
  
- CBRS_FLOATING denetim çubuğu kayan.  
  
- CBRS_FLYBY durum çubuğu düğme hakkındaki bilgileri görüntüler.  
  
- Kullanıcıya CBRS_HIDE_INPLACE denetim çubuğu görüntülenmez.  
  
 *nID*  
 İletişim çubuğu denetiminin kimliği.  
  
 *nIDTemplate*  
 Kaynak Kimliğini `CDialogBar` nesnenin iletişim kutusu şablonu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 CBRS_TOP veya CBRS_BOTTOM hizalamasını stilini belirtmek, iletişim çubuğu genişliği, çerçeve penceresinin, yükseklik, tarafından belirtilen kaynak ise *nIDTemplate*. CBRS_LEFT veya CBRS_RIGHT hizalamasını stilini belirtmek, iletişim çubuğunun yüksekliği, çerçeve penceresinin genişliğini tarafından belirtilen kaynak, ise *nIDTemplate*.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar sınıfı](../../mfc/reference/ccontrolbar-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFormView sınıfı](../../mfc/reference/cformview-class.md)   
 [CControlBar Sınıfı](../../mfc/reference/ccontrolbar-class.md)
