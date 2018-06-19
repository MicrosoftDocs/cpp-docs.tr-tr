---
title: CW2AEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62fd48a34b82e0671d417a882e040a87a7691c01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364004"
---
# <a name="cw2aex-class"></a>CW2AEX sınıfı
Bu sınıf dize dönüştürme makroları tarafından kullanılan `CT2AEX`, `CW2TEX`, `CW2CTEX`, ve `CT2CAEX`ve typedef **CW2A**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_nBufferLength`  
 Çeviri işleminde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](#cw2aex)|Oluşturucu.|  
|[CW2AEX:: ~ CW2AEX](#dtor)|Yok Edicisi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2AEX::operator LPSTR](#operator_lpstr)|Dönüşüm işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2AEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
|[CW2AEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Fazladan işlevsellik gerekli olmadığı sürece kullanmak `CT2AEX`, `CW2TEX`, `CW2CTEX`, `CT2CAEX`, veya **CW2A** kodunuzda.  
  
 Bu sınıf dönüştürme işleminin sonucu depolamak için kullanılan bir sabit boyutlu statik arabellek içerir. Bellek kullanarak sınıfı sonucu statik belleğe sığmayacak kadar büyük olursa ayırır `malloc`, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıfın Döngülerde kullanmak güvenli ve yığın taşması olmaz sağlar.  
  
 Sınıf başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` bağımsız değişkeni ile **E_OUTOFMEMORY**.  
  
 Varsayılan olarak, ATL dönüştürme sınıfları ve makroları geçerli iş parçacığının ANSI kod sayfası dönüştürme için kullanın. Belirli bir dönüştürme için bu davranışı geçersiz kılmak istiyorsanız, sınıf oluşturucusu ikinci parametre olarak kod sayfası belirtin.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 Aşağıdaki typedef bu sınıfa bağlıdır:  
  
- **CW2A**  
  
 Bu metin dönüşüm makroları tartışma için bkz [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="cw2aex"></a>  CW2AEX::CW2AEX  
 Oluşturucu.  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Dönüştürülecek metin dizesi.  
  
 `nCodePage`  
 Kod sayfası dönüştürme gerçekleştirmek için kullanılır. Kod sayfası parametre hakkında bilgi için Windows SDK işlevi bkz [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) daha fazla ayrıntı için.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri işleminde kullanılan arabellek ayırır.  
  
##  <a name="dtor"></a>  CW2AEX:: ~ CW2AEX  
 Yok Edicisi.  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış arabelleğe boşaltır.  
  
##  <a name="m_psz"></a>  CW2AEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CW2AEX::m_szBuffer  
 Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>  CW2AEX::operator LPSTR  
 Dönüşüm işleci.  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesini türü olarak döndürür **LPSTR.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
