---
title: "Ftmbase::createglobalınterfacetable yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc96d8eaff3def90f9ff3e9bd76e0ef067094715
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>FtmBase::CreateGlobalInterfaceTable Yöntemi
Genel arabirim tablosu (GIT) oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `git`  
 Bu işlem tamamlandığında, bir genel arabirim tablo için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için MSDN Kitaplığı'nda "COM başvurusu" konusunun "COM arabirimleri" konu "IGlobalInterfaceTable" konusuna bakın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)