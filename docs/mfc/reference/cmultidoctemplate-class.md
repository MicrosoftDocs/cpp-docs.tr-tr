---
title: CMultiDocTemplate sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b53228b6983c0293eb288cd0f38669d1b5db928
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371588"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate sınıfı
Birden çok belge arabirimi (MDI) uygulayan bir belge şablonu tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMultiDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Oluşturan bir `CMultiDocTemplate` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 MDI uygulamanın ana çerçeve penceresi, her biri bir belgeyi görüntüler kullanıcı sıfır veya daha fazla belge çerçeve pencereleri açabilir bir çalışma alanı olarak kullanır. MDI daha ayrıntılı bir açıklaması için bkz *Windows arabirimi yönergelerine yazılım tasarımı için*.  
  
 Belge şablonu sınıfları üç tür arasındaki ilişkileri tanımlar:  
  
-   Öğesinden türetilen bir belge sınıfı [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Yukarıda listelenen belge sınıfı verileri görüntüleyen bir görünüm sınıfı. Bu sınıftan türetilen [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, veya `CEditView`. (Aynı zamanda `CEditView` doğrudan.)  
  
-   Görünüm içeren bir çerçeve pencere sınıfı. Bir MDI belge şablonu için bu sınıftan türetilen `CMDIChildWnd`, ya da belge çerçeve pencereleri davranışını özelleştirmek gerekmiyorsa kullanabileceğiniz [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) kendi sınıf türetme olmadan doğrudan.  
  
 MDI uygulamanın birden fazla belge türünü destekleyebilir ve belgeler farklı türlerde aynı anda açık olabilir. Uygulamanız destekliyorsa her bir belge türü için bir belge şablonu yok. MDI uygulamanıza elektronik tablolar ve metin belgeleri destekliyorsa, örneğin, uygulamanın iki var. `CMultiDocTemplate` nesneleri.  
  
 Kullanıcı yeni bir belge oluşturduğunda uygulama belge şablonu kullanır. Uygulama birden fazla belge türünü destekliyorsa, framework belge şablonlardan desteklenen belge türlerinin adlarını alır ve bunları yeni dosya iletişim kutusu bir listede görüntüler. Kullanıcı bir belge türü seçtikten sonra uygulama belge sınıf nesnesi, bir çerçeve pencere nesnesi ve bir görünüm nesnesi oluşturur ve bunları birbirine ekler.  
  
 Tüm üye işlevlerini çağırın gerekmez `CMultiDocTemplate` dışındaki Oluşturucusu. Framework tanıtıcıları `CMultiDocTemplate` dahili nesneleri.  
  
 Daha fazla bilgi için `CMultiDocTemplate`, bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="cmultidoctemplate"></a>  CMultiDocTemplate::CMultiDocTemplate  
 Oluşturan bir `CMultiDocTemplate` nesnesi.  
  
```  
CMultiDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDResource`  
 Belge türü ile kullanılan kaynakları Kimliğini belirtir. Bu menü, simge, Hızlandırıcı tablosu ve dize kaynaklarını içerebilir.  
  
 En çok yedi alt dizeler '\n' karakteriyle ayrılmış dize kaynağını oluşur (ancak, sonunda '\n' karakterler gerekli değildir; bir alt dizesi dahil edilmezse '\n' karakteri yer tutucu gerekli); Bu alt dizeler belge türü açıklanmaktadır. Alt dizeler hakkında daha fazla bilgi için bkz: [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynak uygulamanın kaynak dosyası bulunamadı. Örneğin:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 Dize '\n' karakteriyle başlayan unutmayın; ilk alt dizeyi MDI uygulamaları için kullanılmaz ve bu nedenle dahil değildir çünkü budur. Dize Düzenleyicisi'ni kullanarak bu dize düzenleyebilirsiniz; tüm dizeyi tek Dize Düzenleyicisi'nde, bir giriş olarak değil yedi ayrı girişleri olarak görünür.  
  
 Bu kaynak türleri hakkında daha fazla bilgi için bkz: [kaynak düzenleyicileri](../../windows/resource-editors.md).  
  
 `pDocClass`  
 İşaret `CRuntimeClass` belge sınıfın nesnesi. Bu sınıf, bir **CDocument**-türetilmiş sınıf belgelerinizi temsil etmek için tanımlayın.  
  
 `pFrameClass`  
 İşaret `CRuntimeClass` çerçeve penceresi sınıfın nesnesi. Bu sınıf olabilir bir `CMDIChildWnd`-türetilmiş sınıf veya olabilir `CMDIChildWnd` kendisi, belge çerçeve pencereleri için varsayılan davranış istiyorsanız.  
  
 `pViewClass`  
 İşaret `CRuntimeClass` görünüm sınıfın nesnesi. Bu sınıf, bir `CView`-türetilmiş sınıf belgelerinizi görüntülenecek tanımlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dinamik olarak ayırabilir `CMultiDocTemplate` uygulamanızı destekler ve her bir sonrakine her belge türü için nesne `CWinApp::AddDocTemplate` gelen `InitInstance` uygulama sınıfının üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]  
  
 Burada, ikinci bir örnek verilmiştir.  
  
 [!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate sınıfı](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
