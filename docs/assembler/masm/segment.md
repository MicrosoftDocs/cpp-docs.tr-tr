---
description: 'Daha fazla bilgi edinin: SEGMENT'
title: SEGMENT
ms.date: 12/16/2019
f1_keywords:
- SEGMENT
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
ms.openlocfilehash: aeb99080043cbfb13fdec1c2e82df3a6d16b306d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97125599"
---
# <a name="segment"></a>SEGMENT

Bölüm öznitelikleri olan *ad* adlı bir program kesimi tanımlar

## <a name="syntax"></a>Syntax

> *ad* **segmenti** ⟦**ReadOnly**⟧ ⟦*align*⟧ ⟦*birleştirme**⟧ ⟦ ⟧*⟦ ⟧*Özellikler*⟦ **ALIAS (**_dize_**)** ⟧__'__*Class*__'__ \
> *deyimler*\
> *ad* **bitiyor**

#### <a name="parameters"></a>Parametreler

*acaktır*\
Segment için bir başlangıç adresinin seçilebileceği bellek adresleri aralığı. Hizalama türü aşağıdakilerden biri olabilir:

|Hizalama türü|Başlangıç adresi|
|----------------|----------------------|
|**BYTE**|Sonraki kullanılabilir bayt adresi.|
|**SÖZCÜK**|Sonraki kullanılabilir sözcük adresi (sözcük başına 2 bayt).|
|**DWORD**|Sonraki kullanılabilir çift sözcük adresi (çift sözcük başına 4 bayt).|
|**PARAGRAF**|Sonraki kullanılabilir paragraf adresi (paragraf başına 16 bayt).|
|**SAYFASıNDA**|Sonraki kullanılabilir sayfa adresi (sayfa başına 256 bayt).|
|**Hizala**(*n*)|Sonraki kullanılabilir *n*. bayt adresi. Daha fazla bilgi için bkz. açıklamalar bölümü.|

Bu parametre belirtilmemişse, varsayılan olarak **paragraf** kullanılır.

*Birleştir* (yalnızca 32-BIT masa) \
**Ortak**, **yığın**, **ortak**, **bellek**, <em>Adres</em>, **özel**

*kullanın* (yalnızca 32-BIT masa) \
**USE16**, **USE32**, **Flat**

*karakter*\
**Bilgi**, **okuma**, **yazma**, **yürütme**, **paylaşılan**, **nopage**, **NoCache** ve **at**

Bunlar yalnızca COFF için desteklenir ve benzer adın COFF bölüm özelliklerine karşılık gelir (örneğin, **paylaşılan** IMAGE_SCN_MEM_SHARED karşılık gelir). Oku IMAGE_SCN_MEM_READ bayrağını ayarlar. Kullanımdan kaldırılmış salt okunur bayrağı, Bölüm IMG_SCN_MEM_WRITE bayrağını temizleyemez. Herhangi bir *özellik* ayarlandıysa, varsayılan özellikler kullanılmaz ve yalnızca Programcı tarafından belirtilen bayraklar etkin olur.

_dizisinde_\
Bu dize, yayılan COFF nesnesinde bölüm adı olarak kullanılır.  Aynı dış ada sahip birden çok bölüm oluşturur ve farklı MASı segmenti adı vardır.

**/OMF** ile desteklenmez.

*sınıfı*\
Parçaların birleştirilmiş dosyada birleştirilmesi ve sıralanabilmesi gerektiğini belirler. Tipik değerler,, `'DATA'` , `'CODE'` `'CONST'` ve `'STACK'`

## <a name="remarks"></a>Açıklamalar

İçin `ALIGN(n)` , *n* , 1 ile 8192 arasında bir güç olabilir; **/OMF** ile desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
