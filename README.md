            {% if messages %}
                <script>
            // Create an instance of Notyf
                    var notyf = new Notyf(
                        {
                            duration: 5000,
                            dismissible: true,
                            ripple: true,
                            position: { x: 'right', y: 'top' },
                            types: [
                                {
                                    type: 'info',
                                    background: '#2196f3',
                                    icon: false
                                },
                                {
                                    type: 'success',
                                    background: '#4caf50',
                                    icon: {
                                        className: 'material-icons',
                                        tagName: 'i',
                                        text: 'check_circle'
                                    }
                                },
                                {
                                    type: 'warning',
                                    background: '#ff9800',
                                    icon: {
                                        className: 'material-icons',
                                        tagName: 'i',
                                        text: 'warning'
                                    }
                                },
                                {
                                    type: 'error',
                                    background: '#f44336',
                                    icon: {
                                        className: 'material-icons',
                                        tagName: 'i',
                                        text: 'error'
                                    }
                                }
                            ]
                        }
                    );
                </script>
                {% for message in messages %}
                    {% if message.tags == 'success' %}
                        <script>
                            notyf.open({ type: 'success', message: '{{ message }}' });
                        </script>
                    {% elif message.tags == 'error' %}
                        <script>
                            notyf.open({ type: 'error', message: '{{ message }}' });
                        </script>
                    {% elif message.tags == 'info' %}
                        <script>
                            notyf.open({ type: 'info', message: '{{ message }}' });
                        </script>
                    {% elif message.tags == 'warning' %}
                        <script>
                            notyf.open({ type: 'warning', message: '{{ message }}' });
                        </script>
                        </script>
                    {% endif %}
                {% endfor %}
                </script>
            {% endif %}

