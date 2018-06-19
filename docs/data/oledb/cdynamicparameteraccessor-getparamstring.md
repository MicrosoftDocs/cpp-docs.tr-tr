---
title: CDynamicParameterAccessor::GetParamString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor.GetParamString
- GetParamString
- CDynamicParameterAccessor::GetParamString
- ATL.CDynamicParameterAccessor.GetParamString
- ATL::CDynamicParameterAccessor::GetParamString
dev_langs:
- C++
helpviewer_keywords:
- GetParamString method
ms.assetid: 078c2b1c-7072-47c1-a203-f47e75363f91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b8dadcb70dd29f1a70aea288eb0f63b22591561e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091451"
---
# <a name="cdynamicparameteraccessorgetparamstring"></a>CDynamicParameterAccessor::GetParamString
Arabellekte depolanan belirtilen parametresinin dize verilerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
bool GetParamString(DBORDINAL nParam,  
  CSimpleStringA& strOutput) throw();bool GetParamString(DBORDINAL nParam,  
  CSimpleStringW& strOutput) throw();bool GetParamString(DBORDINAL nParam,  
  CHAR* pBuffer,  
   size_t* pMaxLen) throw();bool GetParamString(DBORDINAL nParam,  
  WCHAR* pBuffer,  
   size_t* pMaxLen) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nParam`  
 [in] Parametre numarası (1 uzaklığı). Parametre 0 dönüş değerleri için ayrılmıştır. Numaralı parametre SQL veya saklı yordam çağrısı, sırayla göre parametre dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) bir örnek.  
  
 `strOutput`  
 [out] ANSI (**CSimpleStringA**) veya Unicode (**CSimpleStringW**) dize belirtilen parametre verileri. Türünde bir parametre geçirmelisiniz `CString`, örneğin:  
  
 [!code-cpp[NVC_OLEDB_Consumer#9](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-getparamstring_1.cpp)]  
  
 `pBuffer`  
 [out] ANSI işaretçisine (**CHAR**) veya Unicode (**WCHAR**) dize belirtilen parametre verileri.  
  
 `pMaxLen`  
 [out] Tarafından için arabellek boyutu için bir işaretçi işaret `pBuffer` (karakterleriyle sonlandırma NULL dahil).  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürür **true** başarı veya **false** hatasında.  
  
 Varsa `pBuffer` null, bu yöntem gerekli arabellek boyutunu gösterdiği bellek ayarlar `pMaxLen` ve geri dönüp **true** veri kopyalama olmadan.  
  
 Bu yöntem başarısız olur arabellek `pBuffer` tüm dizeyi alabilecek kadar büyük değil.  
  
 Kullanım `GetParamString` arabelleğinden dizesi parametre verilerini almak için. Kullanım [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) arabelleğinden dize olmayan parametre veri alınamadı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)