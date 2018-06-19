---
title: CSingleDocTemplate sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 413b7b4a7cf11ff7e83596ecc61423d4bc4f0358
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371627"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate sınıfı
Tek belge arabirimi (SDI) uygulayan bir belge şablonu tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Oluşturan bir `CSingleDocTemplate` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 SDI uygulama, bir belgeyi görüntülemek için ana çerçeve penceresi kullanan; aynı anda yalnızca bir belge açık olabilir.  
  
 Belge şablonu sınıfları üç tür arasındaki ilişkiyi tanımlar:  
  
-   Öğesinden türetilen bir belge sınıfı **CDocument**.  
  
-   Yukarıda listelenen belge sınıfı verileri görüntüleyen bir görünüm sınıfı. Bu sınıftan türetilen `CView`, `CScrollView`, `CFormView`, veya `CEditView`. (Aynı zamanda `CEditView` doğrudan.)  
  
-   Görünüm içeren bir çerçeve pencere sınıfı. SDI belge şablonu için bu sınıftan türetilen `CFrameWnd`; ana davranışını özelleştiren gerekmez, çerçeve penceresi, kullanabileceğiniz `CFrameWnd` kendi sınıf türetme olmadan doğrudan.  
  
 Yalnızca bir tane var SDI uygulamanın genellikle bir belge türü, destekler, böylece `CSingleDocTemplate` nesnesi. Aynı anda yalnızca bir belge açık olabilir.  
  
 Tüm üye işlevlerini çağırın gerekmez `CSingleDocTemplate` dışındaki Oluşturucusu. Framework tanıtıcıları `CSingleDocTemplate` dahili nesneleri.  
  
 Kullanma hakkında daha fazla bilgi için `CSingleDocTemplate`, bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>  CSingleDocTemplate::CSingleDocTemplate  
 Oluşturan bir `CSingleDocTemplate` nesnesi.  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIDResource`  
 Belge türü ile kullanılan kaynakları Kimliğini belirtir. Bu menü, simge, Hızlandırıcı tablosu ve dize kaynaklarını içerebilir.  
  
 En çok yedi alt dizeler '\n' karakteriyle ayrılmış dize kaynağını oluşur (bir alt dizesi dahil edilmezse '\n' karakteri yer tutucu olarak gereklidir; ancak, sonunda '\n' karakterler gerekli değildir); Bu alt dizeler belge türü açıklanmaktadır. Alt dizeler hakkında daha fazla bilgi için bkz: [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynak uygulamanın kaynak dosyası bulunamadı. Örneğin:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 Dize Düzenleyicisi'ni kullanarak bu dize düzenleyebilirsiniz; tüm dizeyi tek Dize Düzenleyicisi'nde, bir giriş olarak değil yedi ayrı girişleri olarak görünür.  
  
 Bu kaynak türleri hakkında daha fazla bilgi için bkz: [Dize Düzenleyicisi](../../windows/string-editor.md).  
  
 `pDocClass`  
 İşaret `CRuntimeClass` belge sınıfın nesnesi. Bu sınıf, bir **CDocument**-türetilmiş sınıf belgelerinizi temsil etmek için tanımlayın.  
  
 `pFrameClass`  
 İşaret `CRuntimeClass` çerçeve penceresi sınıfın nesnesi. Bu sınıf olabilir bir `CFrameWnd`-türetilmiş sınıf veya olabilir `CFrameWnd` kendisini varsayılan davranışı, ana çerçeve penceresi istiyorsanız.  
  
 `pViewClass`  
 İşaret `CRuntimeClass` görünüm sınıfın nesnesi. Bu sınıf, bir `CView`-türetilmiş sınıf belgelerinizi görüntülenecek tanımlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Dinamik olarak ayırabilir bir `CSingleDocTemplate` nesne ve ona geçirin `CWinApp::AddDocTemplate` gelen `InitInstance` uygulama sınıfının üye işlevi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DOCKTOOL](../../visual-cpp-samples.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument sınıfı](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate sınıfı](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView sınıfı](../../mfc/reference/cview-class.md)   
 [CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
