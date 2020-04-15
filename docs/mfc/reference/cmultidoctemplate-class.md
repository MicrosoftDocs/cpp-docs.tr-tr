---
title: CMultidocTemplate Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 3b3f239b05b1cf7661929333e2d616acce6bedb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319737"
---
# <a name="cmultidoctemplate-class"></a>CMultidocTemplate Sınıfı

Birden çok belge arabirimini (MDI) uygulayan bir belge şablonu tanımlar.

## <a name="syntax"></a>Sözdizimi

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMultidocTemplate::cmultidoctemplate](#cmultidoctemplate)|Bir `CMultiDocTemplate` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

MDI uygulaması, ana çerçeve penceresini, kullanıcının her biri bir belgeyi görüntüleyen sıfır veya daha fazla belge çerçeve penceresini açabileceği bir çalışma alanı olarak kullanır. MDI'nin daha ayrıntılı bir açıklaması *için, Yazılım Tasarımı için Windows Arabirim Yönergeleri'ne*bakın.

Belge şablonu, üç sınıf türü arasındaki ilişkileri tanımlar:

- [CDocument'den](../../mfc/reference/cdocument-class.md)türediğiniz bir belge sınıfı.

- Yukarıda listelenen belge sınıfından verileri görüntüleyen bir görünüm sınıfı. Bu sınıfı [CView'dan](../../mfc/reference/cview-class.md) `CScrollView` `CFormView`türetebilirsiniz, `CEditView`, veya . (Ayrıca doğrudan `CEditView` kullanabilirsiniz.)

- Görünümü içeren bir çerçeve penceresi sınıfı. Bir MDI belge şablonu için, bu `CMDIChildWnd`sınıfı belge çerçevesi pencerelerinin davranışını özelleştirmeniz gerekmiyorsa, kendi sınıfınızı oluşturmadan doğrudan [CMDIChildWnd'den](../../mfc/reference/cmdichildwnd-class.md) türetebilirsiniz.

Bir MDI uygulaması birden fazla belge türünü destekleyebilir ve farklı türdeki belgeler aynı anda açılabilir. Uygulamanızda desteklediği her belge türü için bir belge şablonu vardır. Örneğin, MDI uygulamanız hem elektronik tabloları hem de metin `CMultiDocTemplate` belgelerini destekliyorsa, uygulamanın iki nesnesi vardır.

Kullanıcı yeni bir belge oluşturduğunda uygulama belge şablonu(lar)ı kullanır. Uygulama birden fazla belge türünü destekliyorsa, çerçeve desteklenen belge türlerinin adlarını belge şablonlarından alır ve bunları Yeni Dosya iletişim kutusundaki bir listede görüntüler. Kullanıcı bir belge türünü seçtikten sonra, uygulama bir belge sınıfı nesnesi, bir çerçeve penceresi nesnesi ve bir görünüm nesnesi oluşturur ve bunları birbirine bağlar.

Oluşturucu `CMultiDocTemplate` dışında herhangi bir üye işlevleri çağırmak gerekmez. Çerçeve `CMultiDocTemplate` nesneleri dahili olarak işler.

Daha fazla `CMultiDocTemplate`bilgi için [Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi'ne](../../mfc/document-templates-and-the-document-view-creation-process.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cdoctemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cmultidoctemplatecmultidoctemplate"></a><a name="cmultidoctemplate"></a>CMultidocTemplate::cmultidoctemplate

Bir `CMultiDocTemplate` nesne inşa eder.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>Parametreler

*nIDKaynak*<br/>
Belge türüyle birlikte kullanılan kaynakların kimliğini belirtir. Bu menü, simge, hızlandırıcı tablo ve dize kaynaklarını içerebilir.

Dize kaynağı ,'\n' karakteriyle ayrılmış en fazla yedi alt dizeden oluşur (bir alt dize dahil değilse yer tutucu olarak '\n' karakteri gereklidir; ancak,'\n' karakterleri izleyerek gerekli değildir); bu alt dizeleri belge türünü açıklar. Alt dizeleri hakkında bilgi için [Bkz. CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring). Bu dize kaynağı, uygulamanın kaynak dosyasında bulunur. Örneğin:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

Dize '\n' karakteriyle başladığını unutmayın; bunun nedeni, ilk alt dizeMin MDI uygulamaları için kullanılmaması ve bu nedenle dahil olmamasıdır. Bu dizeyi dize düzenleyicisini kullanarak edebilirsiniz; dize tüm dizeleri, yedi ayrı girişleri olarak değil, String Düzenleyicisi tek bir giriş olarak görünür.

Bu kaynak türleri hakkında daha fazla bilgi için [Kaynak Düzenleyiciler'e](../../windows/resource-editors.md)bakın.

*pDocClass*<br/>
Belge sınıfının `CRuntimeClass` nesnesine işaret edin. Bu sınıf, `CDocument`belgelerinizi temsil etmek üzere tanımladığınız türetilmiş bir sınıftır.

*pFrameClass*<br/>
Çerçeve penceresi `CRuntimeClass` sınıfının nesnesine işaret ediyor. Bu sınıf türetilmiş bir `CMDIChildWnd`sınıf olabilir `CMDIChildWnd` veya belge çerçevenizin pencereleri için varsayılan davranış istiyorsanız kendisi olabilir.

*pViewClass*<br/>
Görünüm sınıfının `CRuntimeClass` nesnesine işaret edin. Bu sınıf, `CView`belgelerinizi görüntülemek için tanımladığınız türetilmiş bir sınıftır.

### <a name="remarks"></a>Açıklamalar

Uygulamanızın desteklediği `CMultiDocTemplate` her belge türü için dinamik olarak bir `CWinApp::AddDocTemplate` nesne `InitInstance` ayırın ve her bir nesneyi uygulama sınıfınızın üye işlevine geçirin.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

İşte ikinci bir örnektir.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate Sınıfı](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingledocTemplate Sınıfı](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp Sınıfı](../../mfc/reference/cwinapp-class.md)
