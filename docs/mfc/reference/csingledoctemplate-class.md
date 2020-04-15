---
title: CSingledocTemplate Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 5a014b35a6cd2d12367e190e4d6dd689e28eae66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318341"
---
# <a name="csingledoctemplate-class"></a>CSingledocTemplate Sınıfı

Tek belge arabirimini (SDI) uygulayan bir belge şablonu tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSingledocTemplate::CSingledocTemplate](#csingledoctemplate)|Bir `CSingleDocTemplate` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Bir SDİ uygulaması, belgeyi görüntülemek için ana çerçeve penceresini kullanır; aynı anda yalnızca bir belge açılabilir.

Belge şablonu üç tür sınıf arasındaki ilişkiyi tanımlar:

- Türetilmiştir `CDocument`bir belge sınıfı,

- Yukarıda listelenen belge sınıfından verileri görüntüleyen bir görünüm sınıfı. Bu `CView`sınıfı , , `CScrollView` `CFormView`, veya `CEditView`. (Ayrıca doğrudan `CEditView` kullanabilirsiniz.)

- Görünümü içeren bir çerçeve penceresi sınıfı. Bir SDI belge şablonu için, bu `CFrameWnd`sınıfı; ana çerçeve penceresinin davranışını özelleştirmeniz gerekmiyorsa, kendi `CFrameWnd` sınıfınızı türetmeden doğrudan kullanabilirsiniz.

Bir SDI uygulaması genellikle bir belge türünü destekler, `CSingleDocTemplate` bu nedenle yalnızca bir nesnesi vardır. Aynı anda yalnızca bir belge açılabilir.

Oluşturucu `CSingleDocTemplate` dışında herhangi bir üye işlevleri aramak gerekmez. Çerçeve `CSingleDocTemplate` nesneleri dahili olarak işler.

Kullanma `CSingleDocTemplate`hakkında daha fazla bilgi için [Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi'ne](../../mfc/document-templates-and-the-document-view-creation-process.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdoctemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a>CSingledocTemplate::CSingledocTemplate

Bir `CSingleDocTemplate` nesne inşa eder.

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDKaynak*<br/>
Belge türüyle birlikte kullanılan kaynakların kimliğini belirtir. Bu menü, simge, hızlandırıcı tablo ve dize kaynaklarını içerebilir.

Dize kaynağı ,'\n' karakteriyle ayrılmış en fazla yedi alt dizeden oluşur (bir alt dize dahil değilse yer tutucu olarak '\n' karakteri gereklidir; ancak,'\n' karakterleri izleyerek gerekli değildir); bu alt dizeleri belge türünü açıklar. Alt dizeleri hakkında bilgi için [bkz: CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynağı, uygulamanın kaynak dosyasında bulunur. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

Bu dizeyi dize düzenleyicisini kullanarak edebilirsiniz; dize tüm dizeleri, yedi ayrı girişleri olarak değil, String Düzenleyicisi tek bir giriş olarak görünür.

Bu kaynak türleri hakkında daha fazla bilgi için [String Düzenleyicisi'ne](../../windows/string-editor.md)bakın.

*pDocClass*<br/>
Belge sınıfının `CRuntimeClass` nesnesine işaret edin. Bu sınıf, `CDocument`belgelerinizi temsil etmek üzere tanımladığınız türetilmiş bir sınıftır.

*pFrameClass*<br/>
Çerçeve penceresi `CRuntimeClass` sınıfının nesnesine işaret ediyor. Bu sınıf türetilmiş bir `CFrameWnd`sınıf olabilir `CFrameWnd` veya ana çerçeve pencereniz için varsayılan davranış istiyorsanız kendisi olabilir.

*pViewClass*<br/>
Görünüm sınıfının `CRuntimeClass` nesnesine işaret edin. Bu sınıf, `CView`belgelerinizi görüntülemek için tanımladığınız türetilmiş bir sınıftır.

### <a name="remarks"></a>Açıklamalar

Bir `CSingleDocTemplate` nesneyi dinamik olarak ayırın `InitInstance` ve uygulama sınıfınızın üye `CWinApp::AddDocTemplate` işlevinden geçirin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Kişniş Sınıfı](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd Sınıfı](../../mfc/reference/cframewnd-class.md)<br/>
[CMultidocTemplate Sınıfı](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView Sınıfı](../../mfc/reference/cview-class.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
