---
description: 'Daha fazla bilgi edinin: CMultiDocTemplate sınıfı'
title: CMultiDocTemplate sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 70b77c04fed41da3b5f025f6a600b9ecfd4bc89b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331572"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate sınıfı

Birden çok belge arabirimi (MDI) uygulayan bir belge şablonu tanımlar.

## <a name="syntax"></a>Syntax

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>Üyeler

Bu sınıfın üye işlevleri sanal. Belgeler için bkz. [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) ve [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) .

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMultiDocTemplate:: CMultiDocTemplate](#cmultidoctemplate)|Bir `CMultiDocTemplate` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

MDI uygulaması, kullanıcının her biri bir belge görüntüleyen sıfır veya daha fazla belge çerçevesi penceresi içerebilen bir çalışma alanı olarak ana çerçeve penceresini kullanır. MDI hakkında daha ayrıntılı bir açıklama için bkz. *yazılım tasarımı Için Windows arabirim yönergeleri*.

Belge şablonu, üç tür sınıf arasındaki ilişkileri tanımlar:

- [CDocument](../../mfc/reference/cdocument-class.md)sınıfından türettiğiniz bir belge sınıfı.

- Yukarıda listelenen belge sınıfından verileri görüntüleyen bir görünüm sınıfı. Bu sınıfı [CView](../../mfc/reference/cview-class.md),,, veya sınıfından türetebilirsiniz `CScrollView` `CFormView` `CEditView` . (Doğrudan de kullanabilirsiniz `CEditView` .)

- Görünümü içeren bir çerçeve pencere sınıfı. Bir MDI belge şablonu için, bu sınıfı öğesinden türetebilirsiniz `CMDIChildWnd` veya belge çerçevesi pencerelerinin davranışını özelleştirmeniz gerekmiyorsa, kendi sınıfınızı türetmeksizin doğrudan [Cmdıbnd](../../mfc/reference/cmdichildwnd-class.md) kullanabilirsiniz.

Bir MDI uygulaması birden fazla belge türünü destekleyebilir ve farklı türlerdeki belgeler aynı anda açık olabilir. Uygulamanızın desteklediği her belge türü için bir belge şablonu vardır. Örneğin, MDI uygulamanız hem elektronik tabloları hem de metin belgelerini destekliyorsa, uygulamanın iki `CMultiDocTemplate` nesnesi vardır.

Uygulama, Kullanıcı yeni bir belge oluşturduğunda belge şablonlarını kullanır. Uygulama birden fazla belge türünü destekliyorsa, çerçeve belge şablonlarından desteklenen belge türlerinin adlarını alır ve dosya yeni iletişim kutusunda bir listede görüntüler. Kullanıcı bir belge türünü seçtikten sonra, uygulama bir belge sınıfı nesnesi, bir çerçeve penceresi nesnesi ve bir görünüm nesnesi oluşturur ve bunları birbirlerine ekler.

Oluşturucu dışında herhangi bir üye işlevini çağırmanız gerekmez `CMultiDocTemplate` . Çerçeve `CMultiDocTemplate` nesneleri dahili olarak işler.

Hakkında daha fazla bilgi için `CMultiDocTemplate` bkz. [Belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a> CMultiDocTemplate:: CMultiDocTemplate

Bir `CMultiDocTemplate` nesnesi oluşturur.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Belge türüyle kullanılan kaynakların KIMLIĞINI belirtir. Bu, menü, simge, Hızlandırıcı tablosu ve dize kaynakları içerebilir.

Dize kaynağı, ' \n ' karakteriyle ayrılmış en fazla yedi alt dizeden oluşur (bir alt dizenin dahil olmaması halinde "\n" karakteri yer tutucu olarak gereklidir; ancak sondaki ' \n ' karakterleri gerekli değildir); Bu alt dizeler belge türünü anlatmaktadır. Alt dizeler hakkında daha fazla bilgi için bkz. [CDocTemplate:: GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynağı, uygulamanın kaynak dosyasında bulunur. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

İlk alt dize MDI uygulamaları için kullanılmadığından dize bir ' \n ' karakteriyle başlar ve bu nedenle dahil değildir. Bu dizeyi dize düzenleyicisini kullanarak düzenleyebilirsiniz; Tüm dize, dize düzenleyicisinde yedi ayrı girdi olarak değil tek bir girdi olarak görünür.

Bu kaynak türleri hakkında daha fazla bilgi için bkz. [kaynak düzenleyicileri](../../windows/resource-editors.md).

*pDocClass*<br/>
`CRuntimeClass`Belge sınıfının nesnesine işaret eder. Bu sınıf, `CDocument` belgelerinizi temsil etmek için tanımladığınız bir türetilmiş sınıftır.

*pFrameClass*<br/>
`CRuntimeClass`Çerçeve pencere sınıfının nesnesine işaret eder. Bu sınıf `CMDIChildWnd` , bir türetilmiş sınıf olabilir veya `CMDIChildWnd` belge çerçeve pencereleri için varsayılan davranışı istiyorsanız kendisi olabilir.

*pViewClass*<br/>
`CRuntimeClass`Görünüm sınıfının nesnesine işaret eder. Bu sınıf, `CView` belgelerinizi göstermek için tanımladığınız bir türetilmiş sınıftır.

### <a name="remarks"></a>Açıklamalar

`CMultiDocTemplate`Uygulamanızın desteklediği her belge türü için dinamik olarak bir nesne ayırır ve her birini `CWinApp::AddDocTemplate` `InitInstance` uygulama sınıfınızın üye işlevinden öğesine geçirin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

İkinci bir örnek aşağıda verilmiştir.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate sınıfı](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp sınıfı](../../mfc/reference/cwinapp-class.md)
