---
title: Hangi ATL sınıfları ActiveX denetimi kapsamasını kolaylaştırmak? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f024e9929e916e15b110bfc32bc704c4aef755a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361963"
---
# <a name="which-atl-classes-facilitate-activex-control-containment"></a>Hangi ATL sınıfları ActiveX denetimi kapsamasını kolaylaştırmak?
ATL'ın denetimi barındırma kodu herhangi ATL sınıfları kullanmanızı gerektirmez; yalnızca oluşturabileceğiniz bir **"AtlAxWin80"** penceresi ve gerekirse denetimi barındırma API kullanın (daha fazla bilgi için bkz: **ATL denetimi barındırma API nedir**. Ancak, aşağıdaki sınıflar kapsama özellikleri kullanmak kolaylaştırır.  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Saran bir **"AtlAxWin80"** penceresinde, pencere, bir denetim oluşturma ve/veya denetim penceresine ekleme ve ana bilgisayar nesnesindeki arabirim işaretçileri alma için yöntemleri sağlar.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Saran bir **"AtlAxWinLic80"** penceresinde, pencere, bir denetim oluşturma ve/veya lisanslı denetim penceresine ekleme ve ana bilgisayar nesnesindeki arabirim işaretçileri alma için yöntemleri sağlar.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Bir iletişim kaynağını temel ActiveX denetim sınıfları için temel sınıf olarak görev yapar. Bu tür denetimler diğer ActiveX denetimlerini içerebilir.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Bir iletişim kaynağını temel iletişim kutusu sınıfları için temel sınıf olarak görev yapar. Bu tür iletişim kutuları ActiveX denetimlerini içerebilir.|  
|[CWindow](../atl/reference/cwindow-class.md)|Bir yöntem sağlar [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), döndürecektir bir arabirim işaretçisi bir denetimde ana penceresinin Kimliğini verilen. Ayrıca, Windows API sarmalayıcıları kullanıma sunulan `CWindow` pencere yönetimi genellikle daha kolay.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)

