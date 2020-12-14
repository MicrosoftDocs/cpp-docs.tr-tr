---
description: 'Daha fazla bilgi edinin: TN016: MFC ile C++ birden çok devralmayı kullanma'
title: "TN016: MFC'de C++ Birden Çok Devralmayı Kullanma"
ms.date: 06/28/2018
f1_keywords:
- vc.inheritance
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
ms.openlocfilehash: ac4b082a5dc33e93098453714acd25fbd0c18438
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215956"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016: MFC'de C++ Birden Çok Devralmayı Kullanma

Bu notta Microsoft Foundation Sınıfları birden çok devralmanın (MI) kullanılacağı açıklanmaktadır. Mı, MFC ile kullanılması gerekmez. Mı herhangi bir MFC sınıfında kullanılmaz ve bir sınıf kitaplığı yazmak için gerekli değildir.

Aşağıdaki alt konularda, mı 'nin genel MFC idklarının kullanımını ve mı 'nin bazı kısıtlamalarını kapsayan nasıl etkilediği açıklanır. Bu kısıtlamaların bazıları Genel C++ kısıtlamalarıdır. Diğerleri MFC mimarisine göre uygulanmaktadır.

Bu teknik notun sonunda mı kullanan bir bütün MFC uygulaması bulacaksınız.

## <a name="cruntimeclass"></a>CRuntimeClass

MFC 'nin Kalıcılık ve dinamik nesne oluşturma mekanizmaları, sınıfları benzersiz şekilde tanımlamak için [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) veri yapısını kullanır. MFC, bu yapıların birini uygulamanızdaki her dinamik ve/veya serileştirilebilir sınıfla ilişkilendirir. Bu yapılar, uygulama, türündeki özel statik bir nesne kullanılarak başlatıldığında başlatılır `AFX_CLASSINIT` .

Geçerli uygulama, `CRuntimeClass` mı çalışma zamanı türü bilgilerini desteklemez. Bu, MFC uygulamanızda mı kullanmayacağınız anlamına gelmez. Ancak, birden fazla temel sınıfı olan nesnelerle çalışırken bazı sorumluluklara sahip olursunuz.

[CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof) yöntemi, birden fazla temel sınıfa sahipse nesnenin türünü doğru şekilde belirlemecektir. Bu nedenle, [CObject](../mfc/reference/cobject-class.md) 'i sanal bir temel sınıf olarak kullanamazsınız ve `CObject` [CObject:: Serialize](../mfc/reference/cobject-class.md#serialize) ve [CObject:: operator](../mfc/reference/cobject-class.md#operator_new) gibi üye işlevlerine yapılan tüm çağrılar, C++ ' ın uygun işlev çağrısını ayırt edebilmesi için kapsam niteleyicilerine sahip olmalıdır. Bir program MFC içinde mı kullandığında, `CObject` taban sınıf içeren sınıfın temel sınıflar listesindeki en sol sınıf olması gerekir.

Diğer bir seçenek de işlecini kullanmaktır **`dynamic_cast`** . Bir nesneyi mı ile temel sınıflarından birine atama, derleyicinin sağlanan temel sınıftaki işlevleri kullanmasına zorlar. Daha fazla bilgi için bkz. [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).

## <a name="cobject---the-root-of-all-classes"></a>CObject-tüm sınıfların kökü

Tüm önemli sınıflar sınıfından doğrudan veya dolaylı olarak türetilir `CObject` . `CObject` , hiçbir üye verisi içermez, ancak bazı varsayılan işlevlere sahiptir. Mı kullandığınızda, genellikle iki veya daha fazla `CObject` türetilmiş sınıftan kalıtımla alırsınız. Aşağıdaki örnek, bir sınıfın bir [CFrameWnd](../mfc/reference/cframewnd-class.md) ve bir [CObList](../mfc/reference/coblist-class.md)öğesinden nasıl devralmasını göstermektedir:

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

Bu durumda `CObject` iki kez dahildir. Bu, yöntemlere veya işleçlere yönelik herhangi bir başvuruyu belirsizletmenin bir yolu olması gerektiği anlamına gelir `CObject` . **New işleci** ve [delete işleci](../mfc/reference/cobject-class.md#operator_delete) , belirsizliği ortadan kaldırmak zorunda olan iki işleçtir. Başka bir örnek olarak, aşağıdaki kod derleme zamanında bir hataya neden olur:

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>CObject yöntemlerini yeniden uygulama

İki veya daha fazla türetilmiş temel sınıfa sahip yeni bir sınıf oluşturduğunuzda `CObject` , `CObject` diğer kişilerin kullanmasını istediğiniz yöntemleri yeniden uygulamalısınız. Operatörler **`new`** ve **`delete`** zorunludur ve [döküm](../mfc/reference/cobject-class.md#dump) önerilir. Aşağıdaki örnek, **`new`** ve **`delete`** işleçlerini ve yöntemini yeniden uygular `Dump` :

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

## <a name="virtual-inheritance-of-cobject"></a>CObject 'in sanal devralımı

Neredeyse devralma `CObject` işlevi belirsizliğin sorununu çözerek bu durum böyle değildir. ' De üye verisi olmadığından `CObject` , bir temel sınıf üyesi verilerinin birden çok kopyasını önlemek için sanal devralma gerekmez. Daha önce gösterilen ilk örnekte, `Dump` ve ' de farklı şekilde uygulandığından, sanal yöntem hala belirsizdir `CFrameWnd` `CObList` . Belirsizliği kaldırmanın en iyi yolu, önceki bölümde sunulan önerileri izlemelidir.

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject:: IsKindOf ve Run-Time yazma

İçindeki MFC tarafından desteklenen çalışma zamanı yazma mekanizması `CObject` DECLARE_DYNAMIC, IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, DECLARE_SERIAL ve IMPLEMENT_SERIAL makrolarını kullanır. Bu makrolar, güvenli kayları güvence altına almak için bir çalışma zamanı tür denetimi gerçekleştirebilir.

Bu makrolar yalnızca tek bir temel sınıfı destekler ve devralınan sınıfları çarpmak için sınırlı bir şekilde çalışır. IMPLEMENT_DYNAMIC veya IMPLEMENT_SERIAL içinde belirttiğiniz temel sınıf ilk (veya en soldaki) temel sınıf olmalıdır. Bu yerleştirme, yalnızca sol temel sınıf için tür denetimi yapmanız için izin sağlar. Çalışma zamanı tür sistemi ek temel sınıflar hakkında hiçbir şey bilmez. Aşağıdaki örnekte, çalışma zamanı sistemleri, tür denetimi yapar `CFrameWnd` , ancak hakkında hiçbir şey bilmez `CObList` .

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd ve Ileti eşlemeleri

MFC ileti eşleme sisteminin düzgün çalışması için iki ek gereksinim vardır:

- Yalnızca bir `CWnd` türetilmiş temel sınıf olmalıdır.

- `CWnd`-Türetilmiş taban sınıfı ilk (veya en soldaki) temel sınıf olmalıdır.

Çalışmayacak bazı örnekler şunlardır:

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>Mı kullanan örnek program

Aşağıdaki örnek, ve CWinApp sınıfından türetilmiş bir sınıftan oluşan tek başına bir uygulamadır `CFrameWnd` . [](../mfc/reference/cwinapp-class.md) Bir uygulamayı bu şekilde yapınızı öneririz, ancak bu bir sınıfa sahip en küçük MFC uygulamasına bir örnektir.

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

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
