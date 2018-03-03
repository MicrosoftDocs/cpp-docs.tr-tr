---
title: "CA2CAEX sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f579716cff70d0c9f20ea0fa0133dcb4d86c8db3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ca2caex-class"></a>CA2CAEX sınıfı
Bu sınıf dize dönüşüm makroları tarafından kullanılan `CA2CTEX` ve `CT2CAEX`ve typedef **CA2CA**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_nBufferLength`  
 Çeviri işleminde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|Oluşturucu.|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Yok Edicisi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|Dönüşüm işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Fazladan işlevsellik gerekli olmadığı sürece kullanmak `CA2CTEX`, `CT2CAEX`, veya **CA2CA** kendi kodu.  
  
 Bu sınıf Döngülerde güvenlidir ve yığın taşması olmaz. Varsayılan olarak, ATL dönüştürme sınıfları ve makroları geçerli iş parçacığının ANSI kod sayfası dönüştürme için kullanır.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 Aşağıdaki typedef bu sınıfa bağlıdır:  
  
- **CA2CA**  
  
 Bu metin dönüşüm makroları tartışma için bkz [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 Oluşturucu.  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Dönüştürülecek metin dizesi.  
  
 `nCodePage`  
 Bu sınıftaki kullanılmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri için gerekli olan arabellek oluşturur.  
  
##  <a name="dtor"></a>CA2CAEX:: ~ CA2CAEX  
 Yok Edicisi.  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış arabelleğe boşaltır.  
  
##  <a name="m_psz"></a>CA2CAEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="operator_lpcstr"></a>CA2CAEX::operator LPCSTR  
 Dönüşüm işleci.  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesini türü olarak döndürür `LPCSTR`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
