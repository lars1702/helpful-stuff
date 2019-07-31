/*
  A list of emails I've found to test email regexes.
  No 'invalid' emails in the list. I focus on checking that i dont exclude valid addresses. 
  With some exceptions. There are a few technically valid emails you might want to avoid allowing anyway. 
*/

const validEmails = [
  'email@example.com',
  'firstname.lastname@example.com',
  'email@subdomain.example.com',
  'firstname+lastname@example.com',
  'email@123.123.123.123',
  'email@[123.123.123.123]',
  '"email"@example.com',
  '1234567890@example.com',
  'email@example-one.com',
  '_______@example.com',
  'email@example.name',
  'email@example.museum',
  'email@example.co.jp',
  'firstname-lastname@example.com',
  'æøåÆØÅ.HeLLo.from.N0rway@æøå.no',

//https://sqa.stackexchange.com/questions/27440/various-email-addresses-we-use-to-validate-email-address
  'prettyandsimple@example.com',
  'very.common@example.com',
  'disposable.style.email.with+symbol@example.com',
  'other.email-with-dash@example.com',
  'fully-qualified-domain@example.com',
  'x@example.com', //one-letter local-part
  '"very.unusual.@.unusual.com"@example.com',
  '"very.(),:;<>[]\".VERY.\"very@\ \"very\".unusual"@strange.example.com',
  'example-indeed@strange-example.com',
  'admin@mailserver1', //local domain name with no top-level domains(TLD)
  'user@localserver', //also local with no TLD
  "/#!$%&'*+-/=?^_`{}|~@example.org",
  '"()<>[]:,;@\\"!#$%&\'-/=?^_`{}| ~.a"@example.org',
  '" "@example.org', //space between double quotes
  'example@s.solutions', //there are many Internet TLDs, like this one
  'user@tt', //although ICANN highly discourages dotless email addresses
  'user@[IPv6:2001:DB8::1]', //valid to use an ip literal

// https://stackoverflow.com/questions/297420/list-of-email-addresses-that-can-be-used-to-test-a-javascript-validation-script
  'me@example.com',
  'a.nonymous@example.com',
  'name+tag@example.com',
  'name\@tag@example.com', //valid way to use two @ symbols.
  'spaces\ are\ allowed@example.com',
  '"spaces may be quoted"@example.com',
  "!#$%&'*+-/=.?^_`{|}~@[1.0.0.127]",
  "!#$%&'*+-/=.?^_`{|}~@[IPv6:0123:4567:89AB:CDEF:0123:4567:89AB:CDEF]",
  'me(this is a comment)@example.com',

//https://en.wikipedia.org/wiki/List_of_Internet_top-level_domains#Chinese
  'email@tld.translates.to.foshan.xn--1qqw23a', // Many TLDs with non-western characters gets a DNS name like this. Chinese
  'email@tld.translates.to.moskva.xn--11b4c3d', // Cyrillic
  'email@tld.translates.to.arab.xn--ngbrx', // Arabic
]


/* YOUR REGEX HERE*/

const regex = /^.+@[^@]*[^@.](\.[-a-zA-Z0-9]+)$/

/* YOUR REGEX HERE
  The above one one DOES NOT allow
  - removal of top-level domain ('.com', '.org' and so on)
  - most attempts at ip-literal domains, like '[IPv6:0123:4567:89AB:CDEF:0123:4567:89AB:CDEF]' instead of 'gmail.com'
*/


const emailsTestedMap = validEmails.map(value => {
  const isValid = regex.test(value.toLowerCase().trim())
  && !value.includes(".." || ".@" || "@.")
  && value.split("").filter((char) => char === "@").length === 1 // only one @, technically unnecessary
  return [isValid, value]
})

console.log(emailsTestedMap)
