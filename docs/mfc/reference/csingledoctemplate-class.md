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
ms.openlocfilehash: ea133213b8d1d91a6c0932c7f0b7a94c5d5a368a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026771"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate sınıfı
Tek Belgeli Arabirim (SDI) uygulayan bir belge şablonu tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|Oluşturur bir `CSingleDocTemplate` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir SDI uygulaması, bir belgeyi görüntülemek için ana çerçeve penceresinin kullanır; bir kerede yalnızca bir belge açık olabilir.  
  
 Bir belge şablonu sınıfları üç tür arasındaki ilişkiyi tanımlar:  
  
-   Öğesinden türetilen bir belge sınıfı `CDocument`.  
  
-   Yukarıda listelenen belge sınıfı verileri görüntüleyen bir görünüm sınıfı. Bu sınıftan türetilip `CView`, `CScrollView`, `CFormView`, veya `CEditView`. (Ayrıca `CEditView` doğrudan.)  
  
-   Görünüm içeren bir çerçeve penceresi sınıfı. Bir SDI belge şablonu için bu sınıftan türetilen `CFrameWnd`; ana davranışını özelleştirmek gerekmez, çerçeve penceresi, kullanabileceğiniz `CFrameWnd` kendi sınıf türetme olmadan doğrudan.  
  
 Bir SDI uygulaması tek sahiptir, genellikle bir belge, tür destekler `CSingleDocTemplate` nesne. Bir kerede yalnızca bir belge açık olabilir.  
  
 Tüm üye işlevlerini çağırın gerekmez `CSingleDocTemplate` Oluşturucu dışında. Framework tutamaçları `CSingleDocTemplate` dahili olarak nesneleri.  
  
 Kullanma hakkında daha fazla bilgi için `CSingleDocTemplate`, bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>  CSingleDocTemplate::CSingleDocTemplate  
 Oluşturur bir `CSingleDocTemplate` nesne.  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIDResource*  
 Belge türü ile kullanılan kaynakları Kimliğini belirtir. Bu menü, simge, Hızlandırıcı tablosu ve dize kaynakları içerebilir.  
  
 '\N' karakteriyle ayrılmış en fazla yedi alt dizeler dize kaynağını oluşur ('\n' karakteri bir alt dizesi dahil edilmezse yer tutucu olarak gereklidir; ancak, sonunda '\n' karakterler gerekli değildir) Bu alt dizeleri belge türü açıklar. Alt dizeler hakkında daha fazla bilgi için bkz. [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynağı uygulama kaynak dosyası bulunamadı. Örneğin:  
  
```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```
  
 Dize Düzenleyicisi'ni kullanarak bu dizeni düzenleyebilirsiniz; Tüm dize tek bir giriş dizesini Düzenleyicisi'nde, olarak değil yedi ayrı girişleri olarak görünür.  
  
 Bu kaynak türleri hakkında daha fazla bilgi için bkz. [Dize Düzenleyicisi](../../windows/string-editor.md).  
  
 *pDocClass*  
 İşaret `CRuntimeClass` belge sınıfının nesne. Bu sınıf, bir `CDocument`-türetilmiş tanımladığınız belgelerinizi temsil eden sınıf.  
  
 *pFrameClass*  
 İşaret `CRuntimeClass` çerçeve penceresi sınıfın nesnesi. Bu sınıf olabilir bir `CFrameWnd`-derived class veya olabilir `CFrameWnd` kendisi için ana çerçeve penceresinin varsayılan davranışı istiyorsanız.  
  
 *pViewClass*  
 İşaret `CRuntimeClass` nesne görünüm sınıfı. Bu sınıf, bir `CView`-türetilmiş sınıf belgelerinizi görüntülenecek tanımlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 Dinamik olarak ayırabilir bir `CSingleDocTemplate` nesne ve geçirin `CWinApp::AddDocTemplate` gelen `InitInstance` uygulama sınıfının üye işlevi.  
  
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
