---
description: 'Daha fazla bilgi edinin: CSingleDocTemplate sınıfı'
title: CSingleDocTemplate sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 611cada1c90fa776bafb78f0856658cd1bd0a8e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264628"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate sınıfı

Tek belge arabirimini (SDI) uygulayan bir belge şablonu tanımlar.

## <a name="syntax"></a>Syntax

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSingleDocTemplate:: CSingleDocTemplate](#csingledoctemplate)|Bir `CSingleDocTemplate` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bir SDI uygulaması, bir belgeyi göstermek için ana çerçeve penceresini kullanır; tek seferde yalnızca bir belge açık olabilir.

Belge şablonu, üç sınıf türü arasındaki ilişkiyi tanımlar:

- İçinden türettiğiniz bir belge sınıfı `CDocument` .

- Yukarıda listelenen belge sınıfından verileri görüntüleyen bir görünüm sınıfı. Bu sınıfı,, veya öğesinden türetebilirsiniz `CView` `CScrollView` `CFormView` `CEditView` . (Doğrudan de kullanabilirsiniz `CEditView` .)

- Görünümü içeren bir çerçeve pencere sınıfı. Bir SDI belge şablonu için, bu sınıfı öğesinden türetebilirsiniz `CFrameWnd` ; ana çerçeve penceresinin davranışını özelleştirmeniz gerekmiyorsa, `CFrameWnd` kendi sınıfınızı türetmeden doğrudan kullanabilirsiniz.

Bir SDI uygulaması genellikle tek bir nesne türünü destekler, bu nedenle yalnızca bir `CSingleDocTemplate` nesnesi vardır. Tek seferde yalnızca bir belge açık olabilir.

Oluşturucu dışında herhangi bir üye işlevini çağırmanız gerekmez `CSingleDocTemplate` . Çerçeve `CSingleDocTemplate` nesneleri dahili olarak işler.

Kullanma hakkında daha fazla bilgi için `CSingleDocTemplate` bkz. [Belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a> CSingleDocTemplate:: CSingleDocTemplate

Bir `CSingleDocTemplate` nesnesi oluşturur.

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Belge türüyle kullanılan kaynakların KIMLIĞINI belirtir. Bu, menü, simge, Hızlandırıcı tablosu ve dize kaynakları içerebilir.

Dize kaynağı, ' \n ' karakteriyle ayrılmış en fazla yedi alt dizeden oluşur (alt dize dahil değilse, "\n" karakteri bir yer tutucu olarak gereklidir; ancak sondaki ' \n ' karakterleri gerekli değildir); Bu alt dizeler belge türünü anlatmaktadır. Alt dizeler hakkında daha fazla bilgi için bkz. [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynağı, uygulamanın kaynak dosyasında bulunur. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

Bu dizeyi dize düzenleyicisini kullanarak düzenleyebilirsiniz; Tüm dize, dize düzenleyicisinde yedi ayrı girdi olarak değil tek bir girdi olarak görünür.

Bu kaynak türleri hakkında daha fazla bilgi için bkz. [dize düzenleyici](../../windows/string-editor.md).

*pDocClass*<br/>
`CRuntimeClass`Belge sınıfının nesnesine işaret eder. Bu sınıf, `CDocument` belgelerinizi temsil etmek için tanımladığınız bir türetilmiş sınıftır.

*pFrameClass*<br/>
`CRuntimeClass`Çerçeve penceresi sınıfının nesnesine işaret eder. Bu sınıf `CFrameWnd` , bir türetilmiş sınıf olabilir veya `CFrameWnd` ana çerçeve pencerenizin varsayılan davranışını istiyorsanız kendisi olabilir.

*pViewClass*<br/>
`CRuntimeClass`Görünüm sınıfının nesnesine işaret eder. Bu sınıf, `CView` belgelerinizi göstermek için tanımladığınız bir türetilmiş sınıftır.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi dinamik olarak ayırın `CSingleDocTemplate` ve `CWinApp::AddDocTemplate` `InitInstance` uygulama sınıfınızın üye işlevinden geçirin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate sınıfı](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView sınıfı](../../mfc/reference/cview-class.md)<br/>
[CWinApp sınıfı](../../mfc/reference/cwinapp-class.md)
