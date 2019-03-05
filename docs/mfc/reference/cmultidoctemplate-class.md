---
title: CMultiDocTemplate sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 5fefe91fa2067831c0263146ff3b2cd143b9c647
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284261"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate sınıfı

Çok Belgeli Arabirim (MDI) uygulayan bir belge şablonu tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|Oluşturur bir `CMultiDocTemplate` nesne.|

## <a name="remarks"></a>Açıklamalar

Bir MDI uygulaması ana çerçeve penceresinin her biri bir belgeyi görüntüler kullanıcı sıfır veya daha fazla belge çerçeve pencereleri açabilirsiniz bir çalışma alanı olarak kullanır. MDI daha ayrıntılı bir açıklaması için bkz. *yazılım tasarımı için Windows arabirimi yönergelerine*.

Üç tür sınıflar arasındaki ilişkileri bir belge şablonu tanımlar:

- Öğesinden türetilen bir belge sınıfı [CDocument](../../mfc/reference/cdocument-class.md).

- Yukarıda listelenen belge sınıfı verileri görüntüleyen bir görünüm sınıfı. Bu sınıftan türetilip [CView](../../mfc/reference/cview-class.md), `CScrollView`, `CFormView`, veya `CEditView`. (Ayrıca `CEditView` doğrudan.)

- Görünüm içeren bir çerçeve penceresi sınıfı. Bir MDI belge şablonu için bu sınıftan türetilen `CMDIChildWnd`, ya da belge çerçeve pencereleri davranışını özelleştirmek gerekmiyorsa, kullanabileceğiniz [Cmdıchildwnd](../../mfc/reference/cmdichildwnd-class.md) kendi sınıf türetme olmadan doğrudan.

Bir MDI uygulaması birden fazla belge türünü destekleyebilir ve aynı anda farklı türde açık olabilir. Uygulamanızın desteklediği her bir belge türü için bir belge şablonu vardır. MDI uygulamanıza elektronik hem metin belgeleri destekliyorsa, örneğin, uygulama iki içeren `CMultiDocTemplate` nesneleri.

Kullanıcı yeni bir belge oluşturduğunda, uygulamanın belge şablonlarını kullanır. Uygulama birden fazla belge türünü destekliyorsa, framework belge şablonlarından desteklenen belge türlerinin adlarını alır ve bunları bir listede yeni dosya iletişim kutusu görüntüler. Kullanıcı bir belge türü seçtikten sonra uygulama belge sınıf nesnesi, bir çerçeve pencere nesnesi ve bir görünüm nesnesi oluşturur ve bunları birbirine ekler.

Herhangi bir üye işlevlerini çağırmaya gerek kalmayacak `CMultiDocTemplate` Oluşturucu dışında. Framework tutamaçları `CMultiDocTemplate` dahili olarak nesneleri.

Daha fazla bilgi için `CMultiDocTemplate`, bkz: [belge şablonları ve belge/görünüm oluşturma işlemi](../../mfc/document-templates-and-the-document-view-creation-process.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cmultidoctemplate"></a>  CMultiDocTemplate::CMultiDocTemplate

Oluşturur bir `CMultiDocTemplate` nesne.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDResource*<br/>
Belge türü ile kullanılan kaynakları Kimliğini belirtir. Bu menü, simge, Hızlandırıcı tablosu ve dize kaynakları içerebilir.

'\N' karakteriyle ayrılmış en fazla yedi alt dizeler dize kaynağını oluşur ('\n' karakteri bir alt dizesi değilse, bir yer tutucu gereklidir; ancak, sonunda '\n' karakterler gerekli değildir) Bu alt dizeleri belge türü açıklar. Alt dizeler hakkında daha fazla bilgi için bkz: [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynağı uygulama kaynak dosyası bulunamadı. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Unutmayın; dize '\n' karakteri ile başlar. ilk alt dizeyi MDI uygulamaları için kullanılmaz ve bu nedenle dahil olmadığından budur. Dize Düzenleyicisi'ni kullanarak bu dizeni düzenleyebilirsiniz; Tüm dize tek bir giriş dizesini Düzenleyicisi'nde, olarak değil yedi ayrı girişleri olarak görünür.

Bu kaynak türleri hakkında daha fazla bilgi için bkz. [kaynak düzenleyicileri](../../windows/resource-editors.md).

*pDocClass*<br/>
İşaret `CRuntimeClass` belge sınıfının nesne. Bu sınıf, bir `CDocument`-türetilmiş tanımladığınız belgelerinizi temsil eden sınıf.

*pFrameClass*<br/>
İşaret `CRuntimeClass` çerçeve pencere sınıfının nesnesi. Bu sınıf olabilir bir `CMDIChildWnd`-derived class veya olabilir `CMDIChildWnd` kendisi, belge çerçeve pencereleri için varsayılan davranışı istiyorsanız.

*pViewClass*<br/>
İşaret `CRuntimeClass` nesne görünüm sınıfı. Bu sınıf, bir `CView`-türetilmiş sınıf belgelerinizi görüntülenecek tanımlayın.

### <a name="remarks"></a>Açıklamalar

Bir dinamik olarak ayırabilir `CMultiDocTemplate` uygulamanızı destekleyen ve her bir sonrakine her bir belge türü için nesne `CWinApp::AddDocTemplate` gelen `InitInstance` uygulama sınıfının üye işlevi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

İkinci bir örnek aşağıda verilmiştir.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate Sınıfı](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
