---
title: DHTML denetimleri için ATL desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 281b767151726f695e23c4cf2b2df26f8690c5c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064002"
---
# <a name="atl-support-for-dhtml-controls"></a>DHTML Denetimleri İçin ATL Desteği

ATL kullanarak dinamik HTML (DHTML) özelliğine sahip bir denetim oluşturabilirsiniz. ATL DHTML denetimi:

- WebBrowser denetimi barındırır.

- , HTML, DHTML denetimi kullanıcı arabirimini (UI) kullanarak belirtir.

- WebBrowser nesne ve onun yöntemleri kendi arabirimi üzerinden erişir [Iwebbrowser2](https://msdn.microsoft.com/library/aa752127.aspx).

- C++ kodu HTML arasındaki iletişimi yönetir.

DHTML denetimi bir ek dağıtım arabirimi içeren dışında DHTML denetimi diğer ATL denetimi için benzer. Aşağıdaki şekilde bkz [DHTML denetim projesinin öğelerini tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md) varsayılan DHTML projede sağlanan arabirimin bir gösterim.

ATL DHTML denetimini bir Web tarayıcısı ya da ActiveX denetimi Test kapsayıcısı gibi diğer kapsayıcı görüntüleyebilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

[DHTML Denetim Projesinin Öğelerini Tanımlama](../atl/identifying-the-elements-of-the-dhtml-control-project.md)<br/>
DHTML denetim projesinin öğelerini açıklar.

[DHTML’den C++ Kodu Çağırma](../atl/calling-cpp-code-from-dhtml.md)<br/>
DHTML denetiminden C++ kodu çağırma bir örnek sağlar.

[ATL DHTML Denetimi Oluşturma](../atl/creating-an-atl-dhtml-control.md)<br/>
DHTML denetimi oluşturma adımları listelenir.

[ATL DHTML Denetimini Test Etme](../atl/testing-the-atl-dhtml-control.md)<br/>
Yapı ve ilk DHTML denetim projesinin test işlemi gösterilmektedir.

[ATL DHTML Denetimini Değiştirme](../atl/modifying-the-atl-dhtml-control.md)<br/>
Denetime işlevsellik ekleme işlemi gösterilmektedir.

[Değiştirilen ATL DHTML denetimini test etme](../atl/testing-the-modified-atl-dhtml-control.md)<br/>
Yapı ve test denetiminin ek işlevlerine gösterilmektedir.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.

