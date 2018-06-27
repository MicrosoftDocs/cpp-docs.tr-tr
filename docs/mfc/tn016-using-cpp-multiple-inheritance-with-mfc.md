---
title: "TN016: MFC'de C++ birden çok devralmayı kullanma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.inheritance
dev_langs:
- C++
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cba37344a2d065c84e196330e3b4f9d859975102
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954865"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016: MFC'de C++ Birden Çok Devralmayı Kullanma
Bu Not Microsoft Foundation sınıflarıyla birden çok devralma (mı) kullanmayı açıklar. MI kullanımını MFC ile gerekli değildir. Her MFC sınıf kullanılmaz ve bir sınıf kitaplığı yazmak için gerekli değildir.  
  
 Aşağıdaki alt konuları mı genel MFC deyimleri yanı sıra bazı mı kısıtlamalarını kapsayan kullanımını nasıl etkilediğini açıklar. Bu kısıtlamalar genel C++ kısıtlamaları bazılarıdır. Diğer MFC mimarisi tarafından kullanılan.  
  
 Bu teknik Not sonunda mı kullandığı tam bir MFC uygulaması bulacaksınız.  
  
## <a name="cruntimeclass"></a>CRuntimeClass  
 Kalıcılığı ve dinamik Nesne oluşturma mekanizmaları MFC kullanım [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) sınıfları benzersiz şekilde tanımlamak için veri yapısı. MFC bu yapıları birini uygulamanızdaki her dinamik ve/veya serileştirilebilir sınıf ile ilişkilendirir. Özel statik nesne türü kullanarak uygulama başlatıldığında, bu yapıları başlatılmış `AFX_CLASSINIT`.  
  
 Geçerli `CRuntimeClass` mı çalışma zamanı türü bilgileri desteklemiyor. Bu, MFC uygulamanızda mı kullanamazsınız gelmez. Ancak, birden fazla temel sınıfı olan nesneler ile çalışırken bazı sorumlulukları vardır.  
  
 [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) yöntemi olmayan doğru belirleyecektir bir nesne türü birden çok taban sınıfı varsa. Bu nedenle, kullanamazsınız [CObject](../mfc/reference/cobject-class.md) sanal bir temel sınıf ve tüm çağrıları olarak `CObject` üye işlevleri gibi [CObject::Serialize](../mfc/reference/cobject-class.md#serialize) ve [CObject::operator yeni](../mfc/reference/cobject-class.md#operator_new)bu C++ uygun işlev çağrısı ayırt etmek için kapsam niteleyicileri olması gerekir. Bir program mı MFC içinde kullandığında içeren sınıf `CObject` temel sınıf listenin en solundaki sınıfında temel sınıflarının olması gerekir.  
  
 Alternatif kullanmaktır `dynamic_cast` işleci. MI, temel sınıflarından biri için olan bir nesne atama işlevleri sağlanan taban sınıf içinde kullanmak için derleyicisi zorlar. Daha fazla bilgi için bkz: [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).  
  
## <a name="cobject---the-root-of-all-classes"></a>CObject - tüm sınıflar kök  
 Tüm önemli sınıfları doğrudan veya dolaylı olarak sınıfından türetilen `CObject`. `CObject` mu herhangi bir üye veri sahip değilse, ancak bazı varsayılan işlevselliğe sahiptir. MI kullandığınızda, genellikle iki veya daha fazla devralır `CObject`-türetilmiş sınıfları. Aşağıdaki örnek öğesinden bir sınıf nasıl devrettiği gösterilmektedir bir [CFrameWnd](../mfc/reference/cframewnd-class.md) ve [CObList](../mfc/reference/coblist-class.md):  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 Bu durumda `CObject` iki kez bulunur. Bu herhangi bir referans belirsizliğini ortadan kaldırmak için bir yol gerektiği anlamına gelir `CObject` yöntemleri ya da işleçler. **New işleci** ve [delete işleci](../mfc/reference/cobject-class.md#operator_delete) disambiguated gereken iki işleçler. Başka bir örnek olarak, aşağıdaki kod, derleme zamanında bir hataya neden olur:  
  
```  
myListWnd.Dump(afxDump);
*// compile time error, CFrameWnd::Dump or CObList::Dump   
```  
  
## <a name="reimplementing-cobject-methods"></a>CObject yöntemleri reimplementing  
 İki veya daha yeni bir sınıf oluştururken sahip `CObject` türetilmiş temel sınıfları, yeniden uygulamalı `CObject` diğer kişilerin kullanmasını istediğiniz yöntemleri. İşleçler **yeni** ve **silmek** zorunludur ve [dökümü](../mfc/reference/cobject-class.md#dump) önerilir. Aşağıdaki örnek reimplements **yeni** ve **silmek** işleçler ve `Dump` yöntemi:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
 { return CFrameWnd:: operator new(nSize);

}  
    void operator delete(void* p)  
 { CFrameWnd:: operator delete(p);

}  
 
    void Dump(CDumpContent& dc)  
 { CFrameWnd::Dump(dc);

    CObList::Dump(dc);

} 
 ...  
};  
```  
  
## <a name="virtual-inheritance-of-cobject"></a>CObject sanal devralma  
 Bu devralma neredeyse görünebilir `CObject` işlevi belirsizlik sorunu, ancak bu durumda değil. Hiçbir üye verileri olduğundan `CObject`, bir temel sınıf üyesi verilerinin birden çok kopya önlemek için sanal devralma gerekmez. Daha önce gösterilen ilk örnekte `Dump` sanal yöntemi olduğundan hala belirsiz içinde farklı uygulanan `CFrameWnd` ve `CObList`. Belirsizliğini kaldırmak için en iyi yolu, önceki bölümde sunulan önerileri izlemektir.  
  
## <a name="cobjectiskindof-and-run-time-typing"></a>CObject::IsKindOf ve çalışma zamanı yazma  
 MFC'de tarafından desteklenen çalışma zamanı yazarak mekanizması `CObject` DECLARE_DYNAMIC, ımplement_dynamıc, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, declare_serıal ve ımplement_serıal makroları kullanır. Bu makroları güvenli downcasts güvence altına almak için bir çalışma zamanı tür denetimi gerçekleştirebilir.  
  
 Bu makroları yalnızca tek bir temel sınıf desteklemek ve Çarp devralınan sınıflar için sınırlı bir şekilde çalışır. Implement_dynamıc veya ımplement_serıal belirtin temel sınıf ilk (veya en solundaki) temel sınıf olmalıdır. Bu yerleştirme tür en solundaki için temel sınıfı yalnızca denetleme olanak sağlar. Çalışma zamanı tür sistemi ek temel sınıfları hakkında hiçbir şey bilirsiniz. Aşağıdaki örnekte, çalışma zamanı sistemleri ne yapacağını yazın karşı denetimi `CFrameWnd`, ancak hiçbir şey hakkında bilirsiniz `CObList`.  
  
```  
class CListWnd : public CFrameWnd,
    public CObList  
{  
    DECLARE_DYNAMIC(CListWnd) 
 ...  
};  
IMPLEMENT_DYNAMIC(CListWnd,
    CFrameWnd)  
```  
  
## <a name="cwnd-and-message-maps"></a>CWnd ve ileti eşlemeleri  
 Doğru çalışması MFC ileti eşlemesi sistemi için iki ek gereksinimler vardır:  
  
-   Koyulmalıdır tek `CWnd`-türetilen temel sınıfı.  
  
-   `CWnd`-Türetilen temel sınıf ilk (veya en solundaki) temel sınıf olması gerekir.  
  
 Çalışmaz bazı örnekler şunlardır:  
  
```  
class CTwoWindows : public CFrameWnd,
    public CEdit  
 { ... }; *// error : two copies of CWnd  
 
class CListEdit : public CObList,
    public CEdit  
 { ... }; *// error : CEdit (derived from CWnd) must be first  
```  
  
## <a name="a-sample-program-using-mi"></a>Örnek mı kullanarak programı  
 Aşağıdaki örnek türetilmiş bir sınıf oluşan tek başına bir uygulamadır `CFrameWnd` ve [CWinApp](../mfc/reference/cwinapp-class.md). Bu şekilde bir uygulamada yapısı, ancak bu, tek bir sınıf olan en küçük MFC Uygulama örneğidir önermiyoruz.  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

