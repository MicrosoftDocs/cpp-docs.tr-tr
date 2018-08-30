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
ms.openlocfilehash: a401cb74c07815f511ad37e53ac5be267029319c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212227"
---
# <a name="preprocessor-directives"></a>Ön işlemci Yönergeleri

Önişlemci yönergeleri, aşağıdaki gibi `#define` ve `#ifdef`, genellikle kaynak programların kolay değiştirilmesini ve farklı yürütme ortamlarında derlemek kolay hale getirmek için kullanılır. Kaynak dosyasındaki yönergeler önişlemciye belirli eylemleri gerçekleştirmesini söyler. Örneğin, önişlemci metin içindeki belirteçleri değiştirin, diğer dosyaların içeriklerini kaynak dosyaya ekleyin veya metnin bölümlerini kaldırarak dosyanın bir kısmının derlemesini bastır. Önişlemci satırları makro genişletmeden daha önce gerçekleştirilen ve tanınan. Bu nedenle makro önişlemci komutu gibi görünen bir şey genişletir, komut önişlemci tarafından tanınmıyor.

Önişlemci deyimleri kaynak dosya deyimleriyle, çıkış sıraları desteklenmez olarak aynı karakter kullanın. Önişlemci deyimlerinde kullanılan karakter kümesi ile aynı olduğu [yürütme karakter kümesi](https://msdn.microsoft.com/a7901c61-524d-47c6-beb6-d9dacc2e72ed). Önişlemci ayrıca negatif karakter değerlerini tanır.

Önişlemci aşağıdaki yönergeleri tanır:

|||||
|-|-|-|-|
|[#define](../preprocessor/hash-define-directive-c-cpp.md)|[#error](../preprocessor/hash-error-directive-c-cpp.md)|[#import](../preprocessor/hash-import-directive-cpp.md)|[#undef](../preprocessor/hash-undef-directive-c-cpp.md)|
|[#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#include](../preprocessor/hash-include-directive-c-cpp.md)|[#using](../preprocessor/hash-using-directive-cpp.md)|
|[#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#line](../preprocessor/hash-line-directive-c-cpp.md)|[#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|
|[#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||

Numara işareti (**#**) gerekir; yönergeyi içeren satırdaki ilk boşluk olmayan karakter olması beyaz boşluk karakterleri numara işaretleri ile yönergenin ilk harfi arasında görünür. Yönergelerden bazıları bağımsız değişkenler veya değerler içerir. Bir yönerge (dışında bir bağımsız değişken veya yönergenin bir parçası olan değer) takip eden herhangi bir metin tek satır açıklama sınırlayıcısı gelmelidir (**//**) veya açıklama sınırlayıcıları içinde yer almalıdır ( __/ \*\*/__). Önişlemci yönergelerini içeren satırların hemen bir ters eğik çizgi ile satır sonu işareti koyarak devam ettirildi (**\\**).

Önişlemci yönergeleri kaynak dosyada her yerde görünebilir, ancak bunlar yalnızca kaynak dosyasının kalanı için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)  
[Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)  
[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)  
