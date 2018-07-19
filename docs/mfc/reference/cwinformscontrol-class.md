---
title: CWinFormsControl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 797903c3f558cff9a0ff5addb689e31ae2adbed7
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026380"
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl sınıfı
Bir Windows Forms denetimlerinin barındırılması için temel işlevleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>Parametreler  
 `TManagedControl`  
 MFC uygulamasında görüntülenecek bir .NET Framework Windows Forms denetimi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows Forms denetimi sarmalayıcı nesneyi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Bir Windows Forms denetimini bir MFC kapsayıcısında oluşturur.|  
|[CWinFormsControl::GetControl](#getcontrol)|Windows Forms denetimini bir işaretçi alır.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows Forms denetimi için bir tanıtıcı alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Değiştirir [CWinFormsControl::GetControl](#getcontrol) ifadelerde.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Bir tür, bir Windows Forms denetimi için bir işaretçi olarak yayınlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWinFormsControl` Sınıfı, bir Windows Forms denetimlerinin barındırılması için temel işlevleri sağlar.  
  
 Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 MFC kodunuzu pencere işleyicileri önbelleğe değil (genellikle depolanan `m_hWnd`). Bazı Windows Forms Denetim Özellikleri gerektiren temel alınan Win32 `Window` yok ve kullanarak yeniden `DestroyWindow` ve `CreateWindow`. MFC Windows Forms uygulaması işler `Destroy` ve `Create` güncelleştirilecek denetim olaylarını `m_hWnd` üyesi.  
  
> [!NOTE]
>  MFC Windows Forms tümleştirme yalnızca MFC (AFXDLL tanımlandığı) ile dinamik olarak bağlama projeleri çalışır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl  
 Bir Windows Forms denetimini bir MFC kapsayıcısında oluşturur.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>Parametreler  
 *pType*  
 Oluşturulacak denetimi veri türü. Olmalıdır bir [türü](https://msdn.microsoft.com/library/system.type) veri türü.  
  
 *dwStyle*  
 Denetime uygulamak için pencere stili. Bir birleşimi belirler [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles). Şu anda yalnızca aşağıdaki stilleri desteklenmektedir: WS_TABSTOP, ws_vısıble ws_dısabled ve WS_GROUP.  
  
 *Rect*  
 A [RECT yapısı](../../mfc/reference/rect-structure1.md) , denetimin sol ve sağ alt köşe koordinatlarını tanımlar (ilk aşırı yükleme yalnızca).  
  
 *nPlaceHolderID*  
 Statik yer tutucu denetimi tanıtıcısı kaynak düzenleyicisinde yerleştirilir. Yeni oluşturulan Windows Forms denetimi, konum, z düzenini ve stili varsayılarak statik denetimi değiştirir (ikinci aşırı yükleme yalnızca).  
  
 *pParentWnd*  
 Üst penceresine bir işaretçi.  
  
 *nID*  
 Yeni oluşturulan denetime atanmış kaynak kimlik numarası.  
  
 *pControl*  
 Bir Windows Forms denetimi ile ilişkilendirilecek bir örneğini [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) nesnesi (yalnızca dördüncü aşırı).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır olmayan bir değer döndürür. İşlem başarısız olursa, sıfır döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir MFC kapsayıcısındaki bir .NET Framework Windows Forms Denetim örneği oluşturur.  
  
 İlk aşırı yükleme yöntemi, bir .NET Framework veri türü kabul eden *pType* böylece MFC bu türün yeni bir nesne örneği oluşturabilir. *pType* olmalıdır bir [türü](https://msdn.microsoft.com/library/system.type) veri türü.  
  
 Yönteminin ikinci aşırı yükleme göre Windows Forms denetimi oluşturur `TManagedControl` şablon parametresinin `CWinFormsControl` sınıfı. Denetimin konumunu ve boyutunu temel `RECT` yapısı, yönteme geçirilen. Yalnızca *dwStyle* stilleri için önemlidir.  
  
 Üçüncü yöntem aşırı yüklemesi statik denetim yok ve kendi konumunu, z düzenini ve stili varsayılarak yerini alan bir Windows Forms denetimi oluşturur. Statik denetim, yalnızca Windows Forms denetimleri için yer tutucu olarak görev yapar. Denetim oluştururken, bu aşırı yükleme stilleri birleştirir *dwStyle* statik denetimin kaynak stillerle.  
  
 Dördüncü yöntemi aşırı yüklemesini zaten oluşturulmuş bir Windows Forms denetiminde geçirmenize olanak *pControl* , MFC kaydırılır. Aynı türden olmalıdır `TManagedControl` şablon parametresinin `CWinFormsControl` sınıfı.  
  
 Bkz: [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Form kullanma örnekleri için denetler.  
  
##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl  
 MFC Windows Forms denetimi sarmalayıcı nesneyi oluşturur.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Windows Forms Denetim örneği çağırdığınızda [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrol"></a>  CWinFormsControl::GetControl  
 Windows Forms denetimini bir işaretçi alır.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows Forms denetimi için bir işaretçi döndürür.  
  
### <a name="example"></a>Örnek  
  Bkz: [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle  
 Windows Forms denetimi için bir tanıtıcı alır.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Windows Forms denetimi için bir tanıtıcı döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetControlHandle` .NET Framework denetim özellikleri içinde depolanmış pencere tanıtıcısı döndüren bir yardımcı yöntemdir. Pencere tanıtıcısı değeri kopyalanır [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) çağrı sırasında [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;  
 Değiştirir [CWinFormsControl::GetControl](#getcontrol) ifadelerde.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç yerini alan bir kullanışlı bir söz dizimi sağlar `GetControl` ifadelerde.  
  
 Windows Forms hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^  
 Bir tür, bir Windows Forms denetimi için bir işaretçi olarak yayınlar.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç geçirir `CWinFormsControl<TManagedControl>` kabul eden bir Windows Forms denetimi işaretçisi işlevleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinFormsDialog sınıfı](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView Sınıfı](../../mfc/reference/cwinformsview-class.md)
