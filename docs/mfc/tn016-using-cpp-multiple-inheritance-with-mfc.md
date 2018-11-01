---
title: "TN016: MFC'de C++ Birden Çok Devralmayı Kullanma"
ms.date: 06/28/2018
f1_keywords:
- vc.inheritance
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
ms.openlocfilehash: 76dc2e856ca7db783ee542aa2dbb498fd4c1a769
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668877"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016: MFC'de C++ Birden Çok Devralmayı Kullanma

Bu Not, birden çok devralma (mı) ile Microsoft Foundation sınıfları kullanmayı açıklar. MI kullanımı ile MFC gerekli değildir. Her MFC sınıf kullanılmaz ve bir sınıf kitaplığı yazmak için gerekli değildir.

MI genel MFC deyimleri yanı sıra bazı kısıtlamalar mı, kapsayan kullanımını nasıl etkilediğini aşağıdaki alt konuları açıklanmaktadır. Bu sınırlamalar genel C++ kısıtlamalar bazılarıdır. Diğer MFC mimarisi tarafından uygulanmaktadır.

Bu teknik Not sonunda mı kullanan tam bir MFC uygulaması bulabilirsiniz.

## <a name="cruntimeclass"></a>CRuntimeClass

Kalıcılığı ve dinamik Nesne oluşturma mekanizmaları MFC kullanımı [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) sınıfları benzersiz olarak tanımlanabilmesi için veri yapısı. MFC biri bu yapılar, uygulamanızdaki her dinamik ve/veya serileştirilebilir sınıf ile ilişkilendirir. Bu yapılar, özel bir statik nesne türü kullanarak uygulama başlatıldığında başlatılır `AFX_CLASSINIT`.

Geçerli uygulaması `CRuntimeClass` mı çalışma zamanı türü bilgileri desteklemez. Bu, MFC uygulamanızda mı kullanamazsınız gelmez. Ancak, birden fazla temel sınıf olan nesneleri ile çalışırken, belirli sorumlulukları gerekir.

[CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) yöntemi değil doğru şekilde belirler bir nesne türü birden çok temel sınıf varsa. Bu nedenle, kullanamazsınız [CObject](../mfc/reference/cobject-class.md) sanal bir temel sınıf ve tüm çağrıları olarak `CObject` üye işlevleri gibi [CObject::Serialize](../mfc/reference/cobject-class.md#serialize) ve [CObject::operator yeni](../mfc/reference/cobject-class.md#operator_new)için bu C++ uygun işlev çağrısını netleştirmek kapsam niteleyicileri olması gerekir. Bir program mı MFC içinde kullandığında, sınıfı içeren `CObject` temel sınıf temel sınıflar listesinde en soldaki sınıfının olması gerekir.

Kullanmaya alternatiftir `dynamic_cast` işleci. MI, temel sınıflarından birine sahip bir nesne atama sağlanan temel sınıfta işlevleri kullanmak için derleyicinin zorlar. Daha fazla bilgi için [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).

## <a name="cobject---the-root-of-all-classes"></a>CObject - tüm sınıflar kökü

Tüm önemli sınıflar sınıfından doğrudan veya dolaylı olarak türetilir `CObject`. `CObject` mu herhangi bir üye veri yok, ancak bazı varsayılan işlevselliğe sahiptir. MI kullandığınızda, genellikle iki veya daha fazla devralır `CObject`-türetilmiş sınıflar. Öğesinden bir sınıf nasıl devralabilir aşağıdaki örnekte gösterildiği bir [CFrameWnd](../mfc/reference/cframewnd-class.md) ve [CObList](../mfc/reference/coblist-class.md):

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

Bu durumda `CObject` iki kez dahildir. Herhangi bir referans ayırt etmek için bir yol gerekir yani `CObject` yöntemleri veya işleçler. **New işleci** ve [delete işleci](../mfc/reference/cobject-class.md#operator_delete) disambiguated gereken iki işleçleridir. Başka bir örnek olarak, aşağıdaki kod, derleme zamanında bir hataya neden olur:

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>CObject yöntemleri reimplementing

İki veya daha fazla olduğundan, yeni bir sınıf oluşturduğunuzda `CObject` temel sınıflar türetilmiş yeniden uygulayın `CObject` diğer kişilerin kullanmasını istediğiniz yöntemleri. İşleçler **yeni** ve **Sil** zorunludur ve [dökümü](../mfc/reference/cobject-class.md#dump) önerilir. Aşağıdaki örnek reimplements **yeni** ve **Sil** işleçler ve `Dump` yöntemi:

```cpp
class CListWnd : public CFrameWnd, public CObList
{
public:
    void* operator new(size_t nSize)
    {
        return CFrameWnd:: operator new(nSize);
    }
    void operator delete(void* p)
    {
        CFrameWnd:: operator delete(p);
    }
    void Dump(CDumpContent& dc)
    {
        CFrameWnd::Dump(dc);
        CObList::Dump(dc);
    }
    // ...
};
```

## <a name="virtual-inheritance-of-cobject"></a>CObject sanal devralma

Bu sanal devralmayı görünebilir `CObject` işlevi belirsizlik sorunu, ancak bu durum geçerli değildir. Hiçbir üye verileri olduğundan `CObject`, bir temel sınıf üye verileri birden çok kopyasını önlemek için sanal devralma gerekmez. Daha önce gösterilen ilk örnekte `Dump` sanal yöntemi belirsiz hala içinde farklı uygulandığından `CFrameWnd` ve `CObList`. Belirsizliğini kaldırmak için en iyi yolu, önceki bölümde verilen önerileri takip etmektir.

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject::IsKindOf ve çalışma zamanı yazma

MFC'de tarafından desteklenen çalışma zamanı yazma mekanizması `CObject` DECLARE_DYNAMIC, ımplement_dynamıc, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, declare_serıal ve ımplement_serıal makrolarını kullanır. Bu makrolar güvenli alt türe çevirme işlemleri güvence altına almak için bir çalışma zamanı tür denetimi gerçekleştirebilir.

Bu makrolar, yalnızca tek bir temel sınıf destekler ve birden çok kez devralınan sınıflar için sınırlı bir şekilde çalışır. Belirlediğiniz ımplement_dynamıc veya ımplement_serıal temel sınıf ilk (veya en soldaki) taban sınıfı olmalıdır. Bu yerleştirme en soldaki yalnızca temel sınıf için denetimi yazmanıza olanak tanır. Çalışma zamanı tür sistemine ek temel sınıflar ile ilgili hiçbir şey öğrenmiş olacaksınız. Aşağıdaki örnekte, çalışma zamanı sistemlerin yapacağı tür karşı denetimini `CFrameWnd`, ancak hiçbir şey hakkında öğrenmiş olacaksınız `CObList`.

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd ve ileti eşlemeleri

Doğru çalışması MFC ileti eşlemesi sistem için iki ek gereksinimi vardır:

- Olmalıdır tek `CWnd`-türetilmiş bir temel sınıf.

- `CWnd`-Türetilmiş temel sınıfın ilk (veya en soldaki) bir temel sınıf olması gerekir.

Çalışmaz bazı örnekleri aşağıda verilmiştir:

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>Örnek programı mı kullanma

Aşağıdaki örnek, türetilen bir sınıf içeren tek başına uygulamadır `CFrameWnd` ve [CWinApp](../mfc/reference/cwinapp-class.md). Uygulamanın bu şekilde yapılandırın, ancak bu, bir sınıfı olan küçük bir MFC uygulaması örneğidir önermiyoruz.

```cpp
#include <afxwin.h>

class CHelloAppAndFrame : public CFrameWnd, public CWinApp
{
public:
    CHelloAppAndFrame() {}

    // Necessary because of MI disambiguity
    void* operator new(size_t nSize)
        { return CFrameWnd::operator new(nSize); }
    void operator delete(void* p)
        { CFrameWnd::operator delete(p); }

    // Implementation
    // CWinApp overrides
    virtual BOOL InitInstance();
    // CFrameWnd overrides
    virtual void PostNcDestroy();
    afx_msg void OnPaint();

    DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)
    ON_WM_PAINT()
END_MESSAGE_MAP()

// because the frame window is not allocated on the heap, we must
// override PostNCDestroy not to delete the frame object
void CHelloAppAndFrame::PostNcDestroy()
{
    // do nothing (do not call base class)
}

void CHelloAppAndFrame::OnPaint()
{
    CPaintDC dc(this);
    CRect rect;
    GetClientRect(rect);

    CString s = "Hello, Windows!";
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));
    dc.SetBkMode(TRANSPARENT);
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);
}

// Application initialization
BOOL CHelloAppAndFrame::InitInstance()
{
    // first create the main frame
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",
        WS_OVERLAPPEDWINDOW, rectDefault))
        return FALSE;

    // the application object is also a frame window
    m_pMainWnd = this;
    ShowWindow(m_nCmdShow);
    return TRUE;
}

CHelloAppAndFrame theHelloAppAndFrame;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
