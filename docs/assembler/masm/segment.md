---
title: SEGMENT
ms.date: 08/30/2018
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: b7344d9cb685e0212748d7835e19f398f14979e7
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74393725"
---
# <a name="segment"></a>SEGMENT

Bölüm öznitelikleri olan *ad* adlı bir program kesimi tanımlar

## <a name="syntax"></a>Sözdizimi

> *ad* **segmenti** ⟦**ReadOnly**⟧ ⟦*align*⟧ ⟦*birleştirme* *⟧ ⟦ ⟧* ⟦ ⟧*Özellikler*⟦ **ALIAS (** _dize_ **)** ⟧ __'__ *Class* __'__ \
> *deyimler*\
> *ad* **bitiyor**

#### <a name="parameters"></a>Parametreler

*align*<br/>
Segment için bir başlangıç adresinin seçilebileceği bellek adresleri aralığı. Hizalama türü aşağıdakilerden biri olabilir:

|Hizalama türü|Başlangıç adresi|
|----------------|----------------------|
|**BAYT**|Sonraki kullanılabilir bayt adresi.|
|**WORD**|Sonraki kullanılabilir sözcük adresi (sözcük başına 2 bayt).|
|**DWORD**|Sonraki kullanılabilir çift sözcük adresi (çift sözcük başına 4 bayt).|
|**PARAGRAF**|Sonraki kullanılabilir paragraf adresi (paragraf başına 16 bayt).|
|**PAGE**|Sonraki kullanılabilir sayfa adresi (sayfa başına 256 bayt).|
|**Hizala**(*n*)|Sonraki kullanılabilir *n*. bayt adresi. Daha fazla bilgi için bkz. açıklamalar bölümü.|

Bu parametre belirtilmemişse, varsayılan olarak **paragraf** kullanılır.

*birleştirme*\
**Ortak**, **yığın**, **ortak**, **bellek**,<em>Adres</em>, **özel**

\ *kullan*
**USE16**, **USE32**, **Flat**

*özellikler*\
**Bilgi**, **okuma**, **yazma**, **yürütme**, **paylaşılan**, **nopage**, **NoCache**ve **at**

Bunlar yalnızca COFF için desteklenir ve benzer adın COFF bölüm özelliklerine karşılık gelir (örneğin, **paylaşılan** IMAGE_SCN_MEM_SHARED karşılık gelir). Oku IMAGE_SCN_MEM_READ bayrağını ayarlar. Kullanımdan kaldırılmış salt okunur bayrağı, Bölüm IMG_SCN_MEM_WRITE bayrağını temizleyemez. Herhangi bir *özellik* ayarlandıysa, varsayılan özellikler kullanılmaz ve yalnızca Programcı tarafından belirtilen bayraklar etkin olur.

_dize_\
Bu dize, yayılan COFF nesnesinde bölüm adı olarak kullanılır.  Aynı dış ada sahip birden çok bölüm oluşturur ve farklı MASı segmenti adı vardır.

**/OMF**ile desteklenmez.

*sınıf*\
Parçaların birleştirilmiş dosyada birleştirilmesi ve sıralanabilmesi gerektiğini belirler. Tipik değerler şunlardır `'DATA'`, `'CODE'`, `'CONST'` ve `'STACK'`

## <a name="remarks"></a>Açıklamalar

`ALIGN(n)`için, *n* , 1 ile 8192 arasında herhangi bir güç olabilir. **/OMF**ile desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)
