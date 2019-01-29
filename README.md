{% for i in pimcore_iterate_block(pimcore_block('accordion')) %}
    {%  if editmode %}
        <span class="edit-control position-static content-box-control" title="Check this box to add a white background.">{{pimcore_checkbox('content-box',{'reload':true})}} <label>{{'Add content box'|trans}}</label></span>
        <span class="edit-control position-static content-box-control" title="Check this box to open text.">{{pimcore_checkbox('isOpen',{'reload':true})}} <label>{{'Open on page load'|trans}}</label></span>
    {% endif %}
    {% if pimcore_checkbox('content-box').ischecked() %}

        <div class="m073-contentbox  m073-contentbox--default">    
            <div id="anchor-elem-{{i}}" class="m022-accordion is-closed js-m022-accordion js-bootstrap {{pimcore_checkbox('isOpen').ischecked?'is-open':''}}" data-bootstrap="base/modules/m022-accordion/js/m022-accordion::initialize">
                <div class="m022-accordion-head js-m022-accordion-head">

                    <h3 class="m022-accordion-title"> {{ pimcore_input('headline',{'placeholder': 'Headline'|trans}) }}</h3>

                    <span class="m022-accordion-icon">
                    </span>
                </div>
                <div class="m022-accordion-content clearfix">
                    {{ pimcore_wysiwyg('text',{'placeholder': 'Description'|trans}) }}
                </div>
            </div> 
        </div>
    {% else %} 
        <div id="anchor-elem-{{i}}" class="m022-accordion is-closed js-m022-accordion js-bootstrap {{pimcore_checkbox('isOpen').ischecked?'is-open':''}}" data-bootstrap="base/modules/m022-accordion/js/m022-accordion::initialize">
            <div class="m022-accordion-head js-m022-accordion-head">
                <h3 class="m022-accordion-title"> {{ pimcore_input('headline_without_container',{'placeholder': 'Headline'|trans}) }}</h3>
                <span class="m022-accordion-icon">
                </span>
            </div>
            <div class="m022-accordion-content clearfix">
                {{ pimcore_wysiwyg('text_without_container',{'placeholder': 'Description'|trans}) }}
            </div>
        </div>
    {% endif %}      
{% endfor %} 
