> Типо гайд на хорошие коммиты
### Кратенько

Они хотят, чтобы так выглядели коммиты:
```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

Опции: 
+ fix: коммиты типа fix исправляет ошибку в вашей кодовой базе, то есть исправление бага;
+ feat: коммит представляет собой нововведение в кодовую базу;
+ BREAKING CHANGE: это footer, который может быть заменён на восклицательный знак после типа/скопа коммита. Он вводит изменение API, которое вызывает сбой в работе либы;
+ Допускаются типы, отличные от fix and feat, такие как: build, chore, ci, docs, style, refactor, perf, test и другие

Scope(область действия) может быть указана для предоставления доп контекста, к примеру:
`feat(parser): add ability to parse arrays`

> Это соглашение (Conventional commits specification) коррелирует с Semantic Versioning. Я честно впервые о таких вещах слышу, но кажется это полезно. 

>**footer** это как **header**, но лежит снизу;
---
## Примеры в действии

#### Commit message with description and breaking change footer (Коммит с описанием и футером)

```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```
#### Commit message with `!` to draw attention to breaking change (Коммит без футера, но с его смысловой заменой)

```
feat!: send an email to the customer when a product is shipped
```

#### Commit message with no body (Без тела)

```
docs: correct spelling of CHANGELOG
```

#### Commit message with scope (Со скопом)

```
feat(lang): add Polish language
```

#### Commit message with multi-paragraph body and multiple footers (Навороченный коммит)

```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```
---
## Небольшое соглашение

> Здесь короче о том как следует понимать английские модальные глаголы

>Авторы, которые следуют этим рекомендациям
>следует включить эту фразу в начало своего документа:
   Ключевые слова «ДОЛЖЕН», «НЕ ДОЛЖЕН», «ТРЕБУЕТСЯ», «ДОЛЖЕН», «ДОЛЖЕН НЕТ", "СЛЕДУЕТ", "НЕ СЛЕДУЕТ", "РЕКОМЕНДУЕТСЯ", "МОЖЕТ" и «ДОПОЛНИТЕЛЬНО» в этом документе следует толковать так, как описано в RFC 2119.

> Ключевые слова, используемые для указания нескольких уровней требований:

1. MUST   This word, or the terms "REQUIRED" or "SHALL", mean that the
   definition is an absolute requirement of the specification.

>Это слово или термины «ТРЕБУЕТСЯ» или «ДОЛЖЕН» означают, что
   определение является абсолютным требованием спецификации.

2. MUST NOT   This phrase, or the phrase "SHALL NOT", mean that the
   definition is an absolute prohibition of the specification.

>Эта фраза или фраза «НЕ ДОЛЖЕН» означает, что
   определение — это абсолютный запрет спецификации.
   
3. SHOULD   This word, or the adjective "RECOMMENDED", mean that there
   may exist valid reasons in particular circumstances to ignore a
   particular item, but the full implications must be understood and
   carefully weighed before choosing a different course.

>Это слово или прилагательное «РЕКОМЕНДУЕТСЯ» означает, что
   могут существовать веские причины в определенных обстоятельствах игнорировать
   конкретный пункт, но все последствия должны быть поняты и
   тщательно взвесьте все, прежде чем выбрать другой курс.

4. SHOULD NOT   This phrase, or the phrase "NOT RECOMMENDED" mean that
   there may exist valid reasons in particular circumstances when the
   particular behavior is acceptable or even useful, but the full
   implications should be understood and the case carefully weighed
   before implementing any behavior described with this label.

>Эта фраза или фраза «НЕ РЕКОМЕНДУЕТСЯ» означает, что
   могут существовать веские причины в определенных обстоятельствах, когда
   определенное поведение приемлемо или даже полезно, но полное
   Необходимо понимать последствия и тщательно взвешивать случай
   перед реализацией любого поведения, описанного с этим ярлыком.

5. MAY   This word, or the adjective "OPTIONAL", mean that an item is
   truly optional.  One vendor may choose to include the item because a
   particular marketplace requires it or because the vendor feels that
   it enhances the product while another vendor may omit the same item.
   An implementation which does not include a particular option MUST be
   prepared to interoperate with another implementation which does
   include the option, though perhaps with reduced functionality. In the
   same vein an implementation which does include a particular option
   MUST be prepared to interoperate with another implementation which
   does not include the option (except, of course, for the feature the
   option provides.)

>Это слово или прилагательное «ДОПОЛНИТЕЛЬНЫЙ» означает, что элемент
   действительно необязательно. Один поставщик может выбрать включить элемент, потому что
   конкретный рынок требует этого или потому что поставщик считает, что
   он улучшает продукт, в то время как другой поставщик может не включать тот же элемент.
   Реализация, которая не включает определенную опцию, ДОЛЖНА быть
   готовы к взаимодействию с другой реализацией, которая делает
   включить эту опцию, хотя, возможно, с ограниченной функциональностью. В том же ключе реализация, которая включает в себя определенную опцию
   ДОЛЖЕН быть готов к взаимодействию с другой реализацией, которая
   не включает опцию (за исключением, конечно, функции
   (опция предусмотрена.)

6. Guidance in the use of these Imperatives (Руководство по использованию этих императивов)

   Imperatives of the type defined in this memo must be used with care
   and sparingly.  In particular, they MUST only be used where it is
   actually required for interoperation or to limit behavior which has
   potential for causing harm (e.g., limiting retransmisssions)  For
   example, they must not be used to try to impose a particular method
   on implementors where the method is not required for
   interoperability.

>Повелительные наклонения, определенные в этой памятке, следует использовать с осторожностью.
   и экономно. В частности, они ДОЛЖНЫ использоваться только там, где это необходимо.
   фактически требуется для взаимодействия или для ограничения поведения, которое имеет
   потенциал для причинения вреда (например, ограничение повторных передач) Для
   например, они не должны использоваться для попытки навязать определенный метод
   на реализаторах, где метод не требуется для
   совместимость.

7. Security Considerations (Вопросы безопасности)

   These terms are frequently used to specify behavior with security
   implications.  The effects on security of not implementing a MUST or
   SHOULD, or doing something the specification says MUST NOT or SHOULD
   NOT be done may be very subtle. Document authors should take the time
   to elaborate the security implications of not following
   recommendations or requirements as most implementors will not have
   had the benefit of the experience and discussion that produced the
   specification.

>Эти термины часто используются для описания поведения в сфере безопасности.
   Последствия. Влияние на безопасность невыполнения ДОЛЖЕН или
   ДОЛЖЕН или делать то, что спецификация НЕ ДОЛЖНА или ДОЛЖНА
   НЕ быть сделано может быть очень тонким. Авторы документа должны выделить время
   для уточнения последствий несоблюдения правил безопасности
   рекомендации или требования, которых большинство разработчиков не будут иметь
   имели преимущество опыта и обсуждения, которые привели к
   спецификация.

8. Acknowledgments

   The definitions of these terms are an amalgam of definitions taken
   from a number of RFCs.  In addition, suggestions have been
   incorporated from a number of people including Robert Ullmann, Thomas
   Narten, Neal McBurnett, and Robert Elz.

>Определения этих терминов представляют собой совокупность определений, взятых
   из ряда RFC. Кроме того, были предложения
   создано из нескольких человек, включая Роберта Ульмана, Томаса
   Нартен, Нил МакБернетт и Роберт Элц.
---
## Непосредственно то, за чем пришли **Спецификация**

[Ссылка на ориг](https://www.conventionalcommits.org/en/v1.0.0/#specification)

1. Коммиты должны начинаться с типа, сопровождаться (опционально) скопом и ! и обязательно с двоеточием и пробелом в конце.
2. Тип feat должен быть использован только тогда, когда коммит содержит новые строки кода
3. Тип fix должен быть использован только тогда, когда коммит содержит исправление косяков
4. Скоуп может быть добавлен после типа. Обязан состоять из существительного описывающего область кода, где произошли изменения. Пример: `fix(parser):`
5. Описание должно следовать сразу за двоеточием и пробелом после префикса типа/области. Описание представляет собой краткое изложение изменений кода, например, исправление: проблемы с разбором массива, когда в строке содержалось несколько пробелов.
6. Тело содержательного коммита может быть представлено после короткого описания, представляя дополнительную контекстуальную информацию об изменениях кода. Текст должен начинаться с одной пустой строки после описания.
7. Тело коммита имеет свободную форму и может состоять из любого количества параграфов, разделенных новой строкой.
8. Один или несколько футеров могут быть представлены через одну пустую строку после тела. Каждый колонтитул ДОЛЖЕН состоять из слова, за которым следует разделитель`:<space>` or `<space>#`, а затем строковое значение (это вдохновлено соглашением о трейлерах git).
9. В маркере футере вместо пробельных символов, например, Acked-by, ДОЛЖНО использоваться - (это помогает отличить раздел нижнего колонтитула от многопараграфного текста). Исключение сделано для слова BREAKING CHANGE, которое также может быть использовано в качестве маркера.
10. Тело футера МОЖЕТ содержать пробелы и новые строки, и разбор должен завершиться, когда будет найдена следующая допустимая пара маркер/разделитель футера.
11. Breaking changes ДОЛЖНЫ быть указаны в префиксе type/scope фиксации или в виде записи в футере.
12. If included as a footer, a breaking change MUST consist of the uppercase text BREAKING CHANGE, followed by a colon, space, and description, e.g., _BREAKING CHANGE: environment variables now take precedence over config files_.
13. Типы, отличные от feat и fix, МОЖНО использовать в сообщениях фиксации, например, `docs: update ref docs.`
