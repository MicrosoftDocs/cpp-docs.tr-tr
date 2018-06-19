---
title: CUserTool sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
dev_langs:
- C++
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59f5ab622d6124e830028ea61a0c77583f76d015
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374759"
---
# <a name="cusertool-class"></a>CUserTool sınıfı
Bir dış uygulama çalıştıran bir menü öğesi bir kullanıcı aracıdır. **Araçları** sekmesinde **Özelleştir** iletişim kutusu ( [CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) kullanıcının kullanıcı araçları ekleme ve adı, komutu, bağımsız değişken belirtmenizi sağlar ve Her kullanıcı aracı için başlangıç dizini.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|Kullanıcı Aracı simgesi belirtilen dikdörtgene çizer.|  
|[CUserTool::GetCommand](#getcommand)|Kullanıcı aracı ile ilişkili komut metni içeren bir dize döndürür.|  
|[CUserTool::GetCommandId](#getcommandid)|Menü öğesi kullanıcı aracının komut Kimliğini döndürür.|  
|[CUserTool::Invoke](#invoke)|Kullanıcı aracı ile ilişkili komutu yürütür.|  
|[CUserTool::Serialize](#serialize)|Okur veya bir arşiv değiştirilmesine veya bu nesneyi yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CUserTool::SetCommand](#setcommand)|Kullanıcı aracı ile ilişkili komut ayarlar.|  
|[CUserTool::SetToolIcon](#settoolicon)|Kullanıcı Aracı simgesi aracı ile ilişkili uygulamayı yükler.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Kullanıcı aracı varsayılan simgesi yükler.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|Kullanıcı aracı komut satırı bağımsız değişkenleri.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Kullanıcı aracı için başlangıç dizini.|  
|[CUserTool::m_strLabel](#m_strlabel)|Menü öğesi için araç görüntülenen aracı adı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanıcı araçları, uygulamanızdaki etkinleştirme hakkında daha fazla bilgi için bkz: [CUserToolsManager sınıfı](../../mfc/reference/cusertoolsmanager-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl bir aracından oluşturulduğunu gösteren bir `CUserToolsManager` nesne, ayarlamak `m_strLabel` üye değişkeni ve kullanıcı aracını çalıştıran uygulama kümesi. Bu kod parçacığını parçası olan [Visual Studio gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxusertool.h  
  
##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon  
 Kullanıcı Aracı simgesi belirtilen dikdörtgen merkezinde çizer.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectImage`  
 Simge görüntülemek için alanının koordinatları belirtir.  
  
##  <a name="getcommand"></a>  CUserTool::GetCommand  
 Kullanıcı aracı ile ilişkili komut metni içeren bir dize döndürür.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru `CString` kullanıcı aracı ile ilişkili komut metni içeren nesne.  
  
##  <a name="getcommandid"></a>  CUserTool::GetCommandId  
 Kullanıcı aracı komut Kimliğini döndürür.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kullanıcı aracı komut kimliği.  
  
##  <a name="invoke"></a>  CUserTool::Invoke  
 Kullanıcı aracı ile ilişkili komutu yürütür.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komut başarıyla yürütülürse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrıları [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) kullanıcı aracı ile ilişkili bir komutu yürütülemedi. Komut boş ise veya varsa işlevi başarısız [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) başarısız olur.  
  
##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon  
 Kullanıcı aracı varsayılan simgesi yükler.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yüklü simgesi için bir tanıtıcı ( `HICON`), veya `NULL` varsayılan simgesini yüklerse.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı tanımlı bir aracı için bir simge aracı yürütülebilir dosyasından yükleyemedi olduğunda framework bu yöntemi çağırır.  
  
 Kendi varsayılan Aracı simgesi sağlamak için bu yöntemi geçersiz kılın.  
  
##  <a name="m_strarguments"></a>  CUserTool::m_strArguments  
 Kullanıcı aracı komut satırı bağımsız değişkenleri.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdığınızda Bu dize aracına geçirilen [CUserTool::Invoke](#invoke) veya bir kullanıcı bu aracı ile ilişkili komutu tıkladığında.  
  
##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory  
 Kullanıcı aracı için başlangıç dizinini belirtir.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değişken çağırdığınızda, aracı içinde yürütür başlangıç dizinini belirtir [CUserTool::Invoke](#invoke) veya bir kullanıcı bu aracı ile ilişkili komutu tıkladığında.  
  
##  <a name="m_strlabel"></a>  CUserTool::m_strLabel  
 Menü öğesi için araç görüntülenen etiketi.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="serialize"></a>  CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `ar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setcommand"></a>  CUserTool::SetCommand  
 Kullanıcı aracını çalıştıran uygulama ayarlar.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszCmd`  
 Yeni uygulama kullanıcı aracı ile ilişkili olduğu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı aracını çalıştıran yeni bir uygulama ayarlamak için bu yöntemi çağırın. Yöntemi, eski simge yok eder ve yeni bir simge verilen uygulamadan yükler. Uygulamayı bir simge yüklenemiyor, çağırarak kullanıcı aracı varsayılan simgesi yükler [CUserTool::LoadDefaultIcon](#loaddefaulticon).  
  
##  <a name="settoolicon"></a>  CUserTool::SetToolIcon  
 Kullanıcı Aracı simgesi Aracı'nı kullanan uygulamayı yükler.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yüklü simgesi için bir tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Menü öğesini gösterilecek simge yüklemek için bu yöntemi çağırın. Bu yöntem, Aracı'nı kullanan yürütülebilir dosyada simgesi arar. Varsayılan bir simge yoksa simgesine sağlanan [CUserTool::LoadDefaultIcon](#loaddefaulticon) onun yerine kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager Sınıfı](../../mfc/reference/cusertoolsmanager-class.md)
