---
description: 'Daha fazla bilgi edinin: DHTML denetimleri için ATL desteği'
title: DHTML Denetimleri İçin ATL Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
ms.openlocfilehash: 7527527bc5574470fd361bae2375c25ce9345f3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148596"
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML Denetimleri İçin ATL Desteği

ATL kullanarak, dinamik HTML (DHTML) özelliğiyle bir denetim oluşturabilirsiniz. ATL DHTML denetimi:

- WebBrowser denetimini barındırır.

- DHTML denetiminin Kullanıcı arabirimini (UI) HTML kullanarak belirtir.

- , [Denetiminden IWebBrowser2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752127\(v=vs.85\))arabirimi aracılığıyla WebBrowser nesnesine ve yöntemlerine erişir.

- C++ kodu ve HTML arasındaki iletişimi yönetir.

Dhtml denetimi başka bir ATL denetimine benzer, ancak DHTML denetimi ek bir dağıtım arabirimi içerir. Varsayılan DHTML projesinde sunulan arabirimlerin bir çizimi için [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md) bölümündeki şekle bakın.

ATL DHTML denetimini bir Web tarayıcısında veya başka bir kapsayıcıda (örneğin, ActiveX denetimi test kapsayıcısı) görüntüleyebilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

[DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md)<br/>
Bir DHTML denetim projesinin öğelerini açıklar.

[DHTML 'den C++ kodu çağırma](../atl/calling-cpp-code-from-dhtml.md)<br/>
Bir DHTML denetiminden C++ kodu çağırma örneği sağlar.

[ATL DHTML denetimi oluşturma](../atl/creating-an-atl-dhtml-control.md)<br/>
DHTML denetimi oluşturma adımlarını listeler.

[ATL DHTML denetimini test etme](../atl/testing-the-atl-dhtml-control.md)<br/>
İlk DHTML denetim projesinin nasıl oluşturulacağını ve test alınacağını gösterir.

[ATL DHTML denetimini değiştirme](../atl/modifying-the-atl-dhtml-control.md)<br/>
Denetime bazı işlevlerin nasıl ekleneceğini gösterir.

[Değiştirilen ATL DHTML denetimini test etme](../atl/testing-the-modified-atl-dhtml-control.md)<br/>
Denetimin eklenen işlevselliğinin nasıl oluşturulduğunu ve test yapıldığını gösterir.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.
