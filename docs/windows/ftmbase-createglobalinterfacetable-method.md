---
title: Ftmbase::createglobalınterfacetable yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de98932420cf5eb0d5b9b13011044e5bfc7b400d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569010"
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>FtmBase::CreateGlobalInterfaceTable Yöntemi
Bir genel arabirim tablosu (GIT) oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *Git*  
 Bu işlem tamamlandığında bir genel arabirim tablosu işaretçisi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için MSDN Kitaplığı'ndaki "COM başvuru" konusunun "COM arabirimleri" konu "IGlobalInterfaceTable" bölümüne bakın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)