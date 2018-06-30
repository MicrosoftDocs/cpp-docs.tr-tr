---
title: Önişlemci yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- directives, preprocessor
- preprocessor, directives
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5621c1a338ea6870d15dca65c303d4ac2bf8c7a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122601"
---
# <a name="preprocessor-directives"></a>Ön işlemci Yönergeleri

Önişlemci yönergeleri gibi `#define` ve **#ifdef**, genellikle kaynak programlar değiştirmek kolay ve farklı bir yürütme ortamlarda derlemek kolay hale getirmek için kullanılır. Kaynak dosyasında yönergeleri belirli eylemleri gerçekleştirmek için önişlemci söyleyin. Örneğin, önişlemci metin belirteçleri değiştirin, diğer dosyaların içeriğini kaynak dosyaya ekleyin veya metin bölümlerini kaldırarak dosya derlenmesini bastır. Önişlemci satırları tanınan ve makrosu genişletme önce gerçekleştirilen. Bu nedenle, bir makro önişlemci komutu gibi görünen bir şey halinde genişler varsa, bu komut önişlemci tarafından tanınmıyor.

Önişlemci deyimleri kaçış dizileri desteklenmiyor özel kaynak dosya deyimleri olarak ayarla aynı karakterini kullanın. Aynı önişlemci deyimlerinde kullanılan karakter kümesidir [yürütme karakter kümesi](http://msdn.microsoft.com/en-us/a7901c61-524d-47c6-beb6-d9dacc2e72ed). Önişlemci da negatif karakter değerleri tanır.

Önişlemci aşağıdaki yönergeleri tanır:

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Sayı işareti (**#**) gerekir; yönergesi içeren satırda ilk alanı renkleri karakter olması sayı işareti ve yönergesi ilk harfini arasında boşluk karakterleri görünebilir. Bağımsız değişken veya değerleri bazı yönergeleri içerir. Tek satırlı açıklama sınırlayıcısı yönergesi (dışında bir bağımsız değişken veya yönergesi parçası olan değer) izleyen herhangi bir metin gelmelidir (**//**) veya açıklama sınırlayıcıları arasına ( __/ \*\*/__).   Önişlemci yönergeleri içeren satırları hemen satır sonu işaretçisi bir ters eğik çizgi ile koyarak devam etti (**\\**).

Önişlemci yönergeleri bir kaynak dosyasında herhangi bir yerde görünebilir, ancak bunlar yalnızca kaynak dosya kalanı için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)  
[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)  
[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)  
