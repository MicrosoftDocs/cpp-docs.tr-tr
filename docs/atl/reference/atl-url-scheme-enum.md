---
title: "ATL_URL_SCHEME numaralandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords: ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
caps.latest.revision: "7.2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1936492f1b140afb762f7db2ce03abe343f0673d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atlurlscheme"></a>ATL_URL_SCHEME  

Bu numaralandırma üyeleri tarafından anlaşılan düzenleri sabitleri sağlamak [CUrl](curl-class.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      enum ATL_URL_SCHEME{  
   ATL_URL_SCHEME_UNKNOWN = -1,  
   ATL_URL_SCHEME_FTP     = 0,  
   ATL_URL_SCHEME_GOPHER  = 1,  
   ATL_URL_SCHEME_HTTP    = 2,  
   ATL_URL_SCHEME_HTTPS   = 3,  
   ATL_URL_SCHEME_FILE    = 4,  
   ATL_URL_SCHEME_NEWS    = 5,  
   ATL_URL_SCHEME_MAILTO  = 6,  
   ATL_URL_SCHEME_SOCKS   = 7  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlutil.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../active-template-library-atl-concepts.md)   
 [CUrl::SetScheme](curl-class.md#setscheme)   
 [CUrl::GetScheme](curl-class.md#getscheme)